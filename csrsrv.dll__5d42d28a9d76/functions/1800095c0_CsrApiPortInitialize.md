# CsrApiPortInitialize

- ea: `0x1800095c0`
- end: `0x1800097db`
- name: `CsrApiPortInitialize`
- size: `539`
- prototype: `__int64 __fastcall(PVOID Reserved6)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008190`

## callees

- `0x180001bb0`
- `0x180007720`
- `0x1800084e0`
- `0x1800095c0`
- `0x18000ab61`
- `0x18000ab80`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180009647`
- `ntdll!RtlAllocateHeap` at `0x180009647`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000968a`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000968a`
- `ntdll!RtlAppendUnicodeToString` at `0x1800096a0`
- `ntdll!RtlAppendUnicodeToString` at `0x1800096b6`
- `ntdll!RtlAppendUnicodeToString` at `0x1800096a0`
- `ntdll!RtlAppendUnicodeToString` at `0x1800096b6`
- `ntdll!RtlCreateUserThread` at `0x18000978b`
- `ntdll!RtlCreateUserThread` at `0x18000978b`
- `ntdll!NtAlpcCreatePort` at `0x180009730`
- `ntdll!NtAlpcCreatePort` at `0x180009730`

## pseudocode

```c
NTSTATUS __fastcall CsrApiPortInitialize(PVOID Reserved6, _QWORD *a2)
{
  USHORT v4; // bx
  NTSTATUS result; // eax
  PVOID v6; // r8
  NTSTATUS v7; // ebx
  __int64 Reserved7; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v9[48]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 Reserved8; // [rsp+88h] [rbp-78h] BYREF
  __int128 v11; // [rsp+98h] [rbp-68h] BYREF
  _OWORD v12[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v13; // [rsp+C8h] [rbp-38h]
  _BYTE v14[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v15; // [rsp+E0h] [rbp-20h]

  Reserved7 = 0;
  v13 = 0;
  memset(v9, 0, 44);
  Reserved8 = 0;
  v11 = 0;
  memset(v12, 0, sizeof(v12));
  memset_0(v14, 0, 0x48u);
  v4 = CsrDirectoryName.Length + 18;
  CsrApiPortName.Buffer = (PWSTR)RtlAllocateHeap(
                                   CsrHeap,
                                   CsrBaseTag + 0x40000,
                                   (unsigned int)CsrDirectoryName.Length + 18);
  if ( !CsrApiPortName.Buffer )
    return -1073741801;
  CsrApiPortName.MaximumLength = v4;
  CsrApiPortName.Length = 0;
  RtlAppendUnicodeStringToString(&CsrApiPortName, &CsrDirectoryName);
  RtlAppendUnicodeToString(&CsrApiPortName, L"\\");
  RtlAppendUnicodeToString(&CsrApiPortName, L"ApiPort");
  result = CsrpGenerateWorldAccessSD(0x120001u, 0, (struct _ACL **)&v11);
  if ( result >= 0 )
  {
    *(_DWORD *)v9 = 48;
    *(_QWORD *)&v9[8] = 0;
    *(_DWORD *)&v9[24] = 0;
    *(_QWORD *)&v9[16] = &CsrApiPortName;
    *(_QWORD *)&v9[32] = v12;
    *(_QWORD *)&v9[40] = 0;
    memset_0(v14, 0, 0x48u);
    v15 = 952;
    result = NtAlpcCreatePort(&CsrApiPort, v9, v14);
    if ( result >= 0 )
    {
      CsrpFreeSecurityContext(&v11);
      LOBYTE(v6) = 1;
      result = RtlCreateUserThread(
                 (PVOID)0xFFFFFFFFFFFFFFFFLL,
                 0,
                 v6,
                 0,
                 0,
                 0,
                 CsrApiRequestThread,
                 Reserved6,
                 &Reserved7,
                 &Reserved8);
      v7 = result;
      if ( result >= 0 )
      {
        CsrAddStaticServerThread(Reserved7, &Reserved8, 16);
        *a2 = Reserved7;
        return v7;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800095c0  mov     [rsp-8+arg_10], rbx
0x1800095c5  push    rbp
0x1800095c6  push    rsi
0x1800095c7  push    rdi
0x1800095c8  lea     rbp, [rsp-30h]
0x1800095cd  sub     rsp, 130h
0x1800095d4  mov     rax, cs:__security_cookie
0x1800095db  xor     rax, rsp
0x1800095de  mov     [rbp+40h+var_20], rax
0x1800095e2  xorps   xmm0, xmm0
0x1800095e5  xor     eax, eax
0x1800095e7  xorps   xmm1, xmm1
0x1800095ea  mov     [rsp+140h+var_F0], rax
0x1800095ef  mov     rdi, rdx
0x1800095f2  mov     [rbp+40h+var_78], rax
0x1800095f6  mov     rsi, rcx
0x1800095f9  xor     edx, edx; Val
0x1800095fb  movups  [rsp+140h+var_D8], xmm0
0x180009600  lea     r8d, [rax+48h]; Size
0x180009604  lea     rcx, [rbp+40h+var_70]; void *
0x180009608  movups  [rsp+140h+var_E8], xmm0
0x18000960d  movups  [rsp+140h+var_D8+0Ch], xmm0
0x180009612  movups  [rbp+40h+var_B8], xmm0
0x180009616  movups  [rbp+40h+var_A8], xmm1
0x18000961a  movups  [rbp+40h+var_98], xmm1
0x18000961e  movups  [rbp+40h+var_88], xmm1
0x180009622  call    memset_0
0x180009627  movzx   ebx, cs:CsrDirectoryName.Length
0x18000962e  mov     edx, cs:CsrBaseTag
0x180009634  add     ebx, 12h
0x180009637  mov     rcx, cs:CsrHeap; HeapHandle
0x18000963e  add     edx, 40000h; Flags
0x180009644  mov     r8d, ebx; Size
0x180009647  call    cs:__imp_RtlAllocateHeap
0x18000964e  nop     dword ptr [rax+rax+00h]
0x180009653  mov     cs:CsrApiPortName.Buffer, rax
0x18000965a  test    rax, rax
0x18000965d  jnz     short loc_180009669
0x18000965f  mov     eax, 0C0000017h
0x180009664  jmp     loc_1800097BB
0x180009669  mov     cs:CsrApiPortName.MaximumLength, bx
0x180009670  lea     rdx, CsrDirectoryName; Source
0x180009677  xor     eax, eax
0x180009679  lea     rbx, CsrApiPortName
0x180009680  mov     rcx, rbx; Destination
0x180009683  mov     cs:CsrApiPortName.Length, ax
0x18000968a  call    cs:__imp_RtlAppendUnicodeStringToString
0x180009691  nop     dword ptr [rax+rax+00h]
0x180009696  lea     rdx, Source; "\\"
0x18000969d  mov     rcx, rbx; Destination
0x1800096a0  call    cs:__imp_RtlAppendUnicodeToString
0x1800096a7  nop     dword ptr [rax+rax+00h]
0x1800096ac  lea     rdx, aApiport; "ApiPort"
0x1800096b3  mov     rcx, rbx; Destination
0x1800096b6  call    cs:__imp_RtlAppendUnicodeToString
0x1800096bd  nop     dword ptr [rax+rax+00h]
0x1800096c2  lea     r8, [rbp+40h+var_A8]
0x1800096c6  xor     edx, edx
0x1800096c8  mov     ecx, 120001h; AccessMask
0x1800096cd  call    CsrpGenerateWorldAccessSD
0x1800096d2  test    eax, eax
0x1800096d4  js      loc_1800097BB
0x1800096da  xor     edx, edx; Val
0x1800096dc  mov     dword ptr [rsp+140h+var_E8], 30h ; '0'
0x1800096e4  lea     rax, [rbp+40h+var_98]
0x1800096e8  mov     qword ptr [rsp+140h+var_E8+8], 0
0x1800096f1  lea     rcx, [rbp+40h+var_70]; void *
0x1800096f5  mov     dword ptr [rsp+140h+var_D8+8], 0
0x1800096fd  mov     qword ptr [rsp+140h+var_D8], rbx
0x180009702  lea     r8d, [rdx+48h]; Size
0x180009706  mov     [rsp+140h+var_C8], rax
0x18000970b  mov     [rbp+40h+var_C0], 0
0x180009713  call    memset_0
0x180009718  lea     r8, [rbp+40h+var_70]
0x18000971c  mov     [rbp+40h+var_60], 3B8h
0x180009724  lea     rdx, [rsp+140h+var_E8]
0x180009729  lea     rcx, CsrApiPort
0x180009730  call    cs:__imp_NtAlpcCreatePort
0x180009737  nop     dword ptr [rax+rax+00h]
0x18000973c  test    eax, eax
0x18000973e  js      short loc_1800097BB
0x180009740  lea     rcx, [rbp+40h+var_A8]
0x180009744  call    CsrpFreeSecurityContext
0x180009749  lea     rax, [rbp+40h+var_B8]
0x18000974d  xor     r9d, r9d; Reserved2
0x180009750  mov     [rsp+140h+Reserved8], rax; Reserved8
0x180009755  mov     r8b, 1; Reserved1
0x180009758  lea     rax, [rsp+140h+var_F0]
0x18000975d  xor     edx, edx; OutThreadHandle
0x18000975f  mov     [rsp+140h+Reserved7], rax; Reserved7
0x180009764  or      rcx, 0FFFFFFFFFFFFFFFFh; ThreadContext
0x180009768  mov     [rsp+140h+Reserved6], rsi; Reserved6
0x18000976d  lea     rax, CsrApiRequestThread
0x180009774  mov     [rsp+140h+Reserved5], rax; Reserved5
0x180009779  mov     [rsp+140h+Reserved4], 0; Reserved4
0x180009782  mov     [rsp+140h+Reserved3], 0; Reserved3
0x18000978b  call    cs:__imp_RtlCreateUserThread
0x180009792  nop     dword ptr [rax+rax+00h]
0x180009797  mov     ebx, eax
0x180009799  test    eax, eax
0x18000979b  js      short loc_1800097BB
0x18000979d  mov     rcx, [rsp+140h+var_F0]
0x1800097a2  lea     rdx, [rbp+40h+var_B8]
0x1800097a6  mov     r8d, 10h
0x1800097ac  call    CsrAddStaticServerThread
0x1800097b1  mov     rax, [rsp+140h+var_F0]
0x1800097b6  mov     [rdi], rax
0x1800097b9  mov     eax, ebx
0x1800097bb  mov     rcx, [rbp+40h+var_20]
0x1800097bf  xor     rcx, rsp; StackCookie
0x1800097c2  call    __security_check_cookie
0x1800097c7  mov     rbx, [rsp+140h+arg_10]
0x1800097cf  add     rsp, 130h
0x1800097d6  pop     rdi
0x1800097d7  pop     rsi
0x1800097d8  pop     rbp
0x1800097d9  retn
```
