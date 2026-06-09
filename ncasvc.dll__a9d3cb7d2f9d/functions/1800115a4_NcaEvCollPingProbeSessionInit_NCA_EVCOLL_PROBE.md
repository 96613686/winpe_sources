# NcaEvCollPingProbeSessionInit(NCA_EVCOLL_PROBE_ *)

- ea: `0x1800115a4`
- end: `0x18001168e`
- name: `?NcaEvCollPingProbeSessionInit@@YAKPEAUNCA_EVCOLL_PROBE_@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(struct NCA_EVCOLL_PROBE_ *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180011744`

## callees

- `0x180004f04`
- `0x180004f34`
- `0x1800115a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011619`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011619`
- `IPHLPAPI!Icmp6CreateFile` at `0x1800115e4`
- `IPHLPAPI!Icmp6CreateFile` at `0x1800115e4`

## pseudocode

```c
__int64 __fastcall NcaEvCollPingProbeSessionInit(struct NCA_EVCOLL_PROBE_ *a1)
{
  char *File; // rax
  DWORD v3; // ebx
  DWORD LastError; // eax
  PVOID *v5; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids);
  File = (char *)Icmp6CreateFile();
  *((_QWORD *)a1 + 5) = File;
  if ( (unsigned __int64)(File - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    *((_OWORD *)a1 + 3) = 0;
    v3 = 0;
    *(_OWORD *)((char *)a1 + 60) = 0;
    *(_OWORD *)((char *)a1 + 76) = 0;
    *(_OWORD *)((char *)a1 + 88) = 0;
LABEL_9:
    v5 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_10;
  }
  LastError = GetLastError();
  v3 = LastError;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids, LastError);
    goto LABEL_9;
  }
LABEL_10:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
    WPP_SF_d(v5[2], 26, &WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x1800115a4  mov     [rsp+arg_0], rbx
0x1800115a9  mov     [rsp+arg_8], rsi
0x1800115ae  push    rdi
0x1800115af  sub     rsp, 20h
0x1800115b3  mov     rdi, rcx
0x1800115b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800115bd  lea     rsi, WPP_GLOBAL_Control
0x1800115c4  cmp     rcx, rsi
0x1800115c7  jz      short loc_1800115E4
0x1800115c9  test    byte ptr [rcx+1Ch], 8
0x1800115cd  jz      short loc_1800115E4
0x1800115cf  mov     rcx, [rcx+10h]
0x1800115d3  lea     r8, WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids
0x1800115da  mov     edx, 18h
0x1800115df  call    WPP_SF_
0x1800115e4  call    cs:__imp_Icmp6CreateFile
0x1800115eb  nop     dword ptr [rax+rax+00h]
0x1800115f0  mov     [rdi+28h], rax
0x1800115f4  dec     rax
0x1800115f7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800115fb  ja      short loc_180011619
0x1800115fd  xorps   xmm0, xmm0
0x180011600  xorps   xmm1, xmm1
0x180011603  movups  xmmword ptr [rdi+30h], xmm0
0x180011607  xor     ebx, ebx
0x180011609  movups  xmmword ptr [rdi+3Ch], xmm0
0x18001160d  xor     eax, eax
0x18001160f  movups  xmmword ptr [rdi+4Ch], xmm1
0x180011613  movups  xmmword ptr [rdi+58h], xmm1
0x180011617  jmp     short loc_180011651
0x180011619  call    cs:__imp_GetLastError
0x180011620  nop     dword ptr [rax+rax+00h]
0x180011625  mov     ebx, eax
0x180011627  mov     rcx, cs:WPP_GLOBAL_Control
0x18001162e  cmp     rcx, rsi
0x180011631  jz      short loc_18001167B
0x180011633  test    byte ptr [rcx+1Ch], 1
0x180011637  jz      short loc_180011658
0x180011639  mov     rcx, [rcx+10h]
0x18001163d  lea     r8, WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids
0x180011644  mov     edx, 19h
0x180011649  mov     r9d, eax
0x18001164c  call    WPP_SF_d
0x180011651  mov     rcx, cs:WPP_GLOBAL_Control
0x180011658  cmp     rcx, rsi
0x18001165b  jz      short loc_18001167B
0x18001165d  test    byte ptr [rcx+1Ch], 8
0x180011661  jz      short loc_18001167B
0x180011663  mov     rcx, [rcx+10h]
0x180011667  lea     r8, WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids
0x18001166e  mov     edx, 1Ah
0x180011673  mov     r9d, ebx
0x180011676  call    WPP_SF_d
0x18001167b  mov     rsi, [rsp+28h+arg_8]
0x180011680  mov     eax, ebx
0x180011682  mov     rbx, [rsp+28h+arg_0]
0x180011687  add     rsp, 20h
0x18001168b  pop     rdi
0x18001168c  retn
```
