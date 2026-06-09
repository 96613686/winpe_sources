# MetSubstituteParamSet(ushort * *,ushort const *,_DIAG_PARAMSET *)

- ea: `0x14005c044`
- end: `0x14005c387`
- name: `?MetSubstituteParamSet@@YAJPEAPEAGPEBGPEAU_DIAG_PARAMSET@@@Z`
- size: `835`
- prototype: `__int64 __fastcall(unsigned __int16 **, const unsigned __int16 *, struct _DIAG_PARAMSET *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14005c390`

## callees

- `0x140020420`
- `0x140022070`
- `0x140056448`
- `0x14005c044`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14005c29d`
- `KERNEL32!HeapAlloc` at `0x14005c29d`
- `KERNEL32!HeapFree` at `0x14005c360`
- `KERNEL32!HeapFree` at `0x14005c360`
- `KERNEL32!GetProcessHeap` at `0x14005c289`
- `KERNEL32!GetProcessHeap` at `0x14005c34c`
- `KERNEL32!GetProcessHeap` at `0x14005c289`
- `KERNEL32!GetProcessHeap` at `0x14005c34c`
- `ntdll!RtlExpandEnvironmentStrings` at `0x14005c255`
- `ntdll!RtlExpandEnvironmentStrings` at `0x14005c2eb`
- `ntdll!RtlExpandEnvironmentStrings` at `0x14005c255`
- `ntdll!RtlExpandEnvironmentStrings` at `0x14005c2eb`
- `ntdll!RtlDestroyEnvironment` at `0x14005c33b`
- `ntdll!RtlDestroyEnvironment` at `0x14005c33b`
- `ntdll!RtlInitUnicodeStringEx` at `0x14005c13b`
- `ntdll!RtlInitUnicodeStringEx` at `0x14005c17e`
- `ntdll!RtlInitUnicodeStringEx` at `0x14005c13b`
- `ntdll!RtlInitUnicodeStringEx` at `0x14005c17e`
- `ntdll!RtlCreateEnvironment` at `0x14005c0c8`
- `ntdll!RtlCreateEnvironment` at `0x14005c0c8`
- `ntdll!RtlNtStatusToDosError` at `0x14005c0de`
- `ntdll!RtlNtStatusToDosError` at `0x14005c151`
- `ntdll!RtlNtStatusToDosError` at `0x14005c194`
- `ntdll!RtlNtStatusToDosError` at `0x14005c1d2`
- `ntdll!RtlNtStatusToDosError` at `0x14005c301`
- `ntdll!RtlNtStatusToDosError` at `0x14005c0de`
- `ntdll!RtlNtStatusToDosError` at `0x14005c151`
- `ntdll!RtlNtStatusToDosError` at `0x14005c194`
- `ntdll!RtlNtStatusToDosError` at `0x14005c1d2`
- `ntdll!RtlNtStatusToDosError` at `0x14005c301`
- `ntdll!RtlSetEnvironmentVariable` at `0x14005c1bc`
- `ntdll!RtlSetEnvironmentVariable` at `0x14005c1bc`

## pseudocode

```c
__int64 __fastcall MetSubstituteParamSet(unsigned __int16 **a1, const unsigned __int16 *a2, struct _DIAG_PARAMSET *a3)
{
  unsigned __int16 *v5; // r14
  signed int v6; // eax
  unsigned int v7; // esi
  int v8; // r9d
  int v9; // eax
  bool v10; // sf
  unsigned int i; // ebx
  int inited; // eax
  signed int v13; // eax
  bool v14; // sf
  int v15; // eax
  bool v16; // sf
  int v17; // eax
  bool v18; // sf
  NTSTATUS v19; // eax
  SIZE_T v20; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v22; // rax
  unsigned __int64 v23; // r8
  bool v24; // sf
  HANDLE v25; // rax
  int v27; // [rsp+20h] [rbp-40h]
  unsigned __int64 v28; // [rsp+30h] [rbp-30h] BYREF
  struct _UNICODE_STRING Value; // [rsp+38h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-18h] BYREF
  PWSTR Environment; // [rsp+B0h] [rbp+50h] BYREF
  unsigned __int64 v33; // [rsp+B8h] [rbp+58h] BYREF

  v5 = 0;
  Environment = 0;
  DestinationString = 0;
  v28 = 0;
  Value = 0;
  v33 = 0;
  if ( !*(_QWORD *)a3 )
  {
    v6 = MetStrCpy(a1, a2);
    v7 = v6;
    if ( v6 >= 0 )
      goto LABEL_56;
    v8 = 187;
LABEL_4:
    v27 = v6;
    goto LABEL_5;
  }
  v7 = 0;
  v9 = RtlCreateEnvironment(0, &Environment);
  if ( v9 >= 0 )
  {
    v6 = 0;
LABEL_10:
    v10 = v6 < 0;
    goto LABEL_11;
  }
  v6 = RtlNtStatusToDosError(v9);
  v10 = v6 < 0;
  if ( v6 > 0 )
  {
    v6 = (unsigned __int16)v6 | 0x80070000;
    goto LABEL_10;
  }
LABEL_11:
  if ( v10 )
  {
    v8 = 193;
    goto LABEL_4;
  }
  if ( !Environment )
  {
    v7 = -2147418113;
    v8 = 194;
    v27 = -2147418113;
    goto LABEL_5;
  }
  for ( i = 0; i < *((_DWORD *)a3 + 2); ++i )
  {
    inited = RtlInitUnicodeStringEx(&DestinationString, *(PCWSTR *)(*(_QWORD *)a3 + 16LL * i));
    if ( inited < 0 )
    {
      v13 = RtlNtStatusToDosError(inited);
      v14 = v13 < 0;
      if ( v13 <= 0 )
        goto LABEL_22;
      v13 = (unsigned __int16)v13 | 0x80070000;
    }
    else
    {
      v13 = 0;
    }
    v14 = v13 < 0;
LABEL_22:
    if ( v14 )
    {
      v8 = 203;
      goto LABEL_39;
    }
    v15 = RtlInitUnicodeStringEx(&Value, *(PCWSTR *)(*(_QWORD *)a3 + 16LL * i + 8));
    if ( v15 < 0 )
    {
      v13 = RtlNtStatusToDosError(v15);
      v16 = v13 < 0;
      if ( v13 <= 0 )
        goto LABEL_28;
      v13 = (unsigned __int16)v13 | 0x80070000;
    }
    else
    {
      v13 = 0;
    }
    v16 = v13 < 0;
LABEL_28:
    if ( v16 )
    {
      v8 = 208;
      goto LABEL_39;
    }
    v17 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
    if ( v17 < 0 )
    {
      v13 = RtlNtStatusToDosError(v17);
      v18 = v13 < 0;
      if ( v13 <= 0 )
        goto LABEL_34;
      v13 = (unsigned __int16)v13 | 0x80070000;
    }
    else
    {
      v13 = 0;
    }
    v18 = v13 < 0;
LABEL_34:
    if ( v18 )
    {
      v8 = 211;
LABEL_39:
      v27 = v13;
      goto LABEL_5;
    }
  }
  v13 = StringCchLengthW(a2, 0x100000u, &v28);
  v7 = v13;
  if ( v13 < 0 )
  {
    v8 = 215;
    goto LABEL_39;
  }
  v19 = RtlExpandEnvironmentStrings(Environment, a2, v28, 0, 0, &v33);
  if ( v19 != -1073741789 )
  {
LABEL_48:
    if ( v19 < 0 )
    {
      v13 = RtlNtStatusToDosError(v19);
      v24 = v13 < 0;
      if ( v13 <= 0 )
      {
LABEL_53:
        if ( v24 )
        {
          v8 = 246;
          goto LABEL_39;
        }
        *a1 = v5;
        v5 = 0;
        goto LABEL_56;
      }
      v13 = (unsigned __int16)v13 | 0x80070000;
    }
    else
    {
      v13 = 0;
    }
    v24 = v13 < 0;
    goto LABEL_53;
  }
  if ( v33 > 0x100000 )
  {
    v7 = -2147024785;
    v8 = 231;
    v27 = -2147024785;
    goto LABEL_5;
  }
  v20 = 2 * v33;
  ProcessHeap = GetProcessHeap();
  v22 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, v20);
  v5 = v22;
  if ( v22 )
  {
    v23 = v28;
    *v22 = 0;
    v19 = RtlExpandEnvironmentStrings(Environment, a2, v23, v22, v33, 0);
    goto LABEL_48;
  }
  v7 = -2147024882;
  v8 = 234;
  v27 = -2147024882;
LABEL_5:
  SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetSubstituteParamSet", v8, v27);
LABEL_56:
  if ( Environment )
    RtlDestroyEnvironment(Environment);
  if ( v5 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v5);
  }
  return v7;
}

```

## disassembly

```asm
0x14005c044  mov     [rsp-38h+arg_8], rbx
0x14005c049  mov     [rsp-38h+arg_0], rcx
0x14005c04e  push    rbp
0x14005c04f  push    rsi
0x14005c050  push    rdi
0x14005c051  push    r12
0x14005c053  push    r13
0x14005c055  push    r14
0x14005c057  push    r15
0x14005c059  mov     rbp, rsp
0x14005c05c  sub     rsp, 60h
0x14005c060  xor     eax, eax
0x14005c062  xorps   xmm0, xmm0
0x14005c065  xorps   xmm1, xmm1
0x14005c068  mov     r12, r8
0x14005c06b  mov     r13, rdx
0x14005c06e  mov     r14d, eax
0x14005c071  mov     [rbp+Environment], rax
0x14005c075  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14005c079  mov     [rbp+var_30], rax
0x14005c07d  movups  xmmword ptr [rbp+Value.Length], xmm1
0x14005c081  mov     [rbp+arg_18], rax
0x14005c085  cmp     [r8], rax
0x14005c088  jnz     short loc_14005C0C0
0x14005c08a  call    ?MetStrCpy@@YAJPEAPEAGPEBG@Z; MetStrCpy(ushort * *,ushort const *)
0x14005c08f  mov     esi, eax
0x14005c091  test    eax, eax
0x14005c093  jns     loc_14005C332
0x14005c099  mov     r9d, 0BBh
0x14005c09f  mov     dword ptr [rsp+60h+var_40], eax
0x14005c0a3  mov     ecx, 1; Level
0x14005c0a8  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x14005c0af  lea     r8, aMetsubstitutep; "MetSubstituteParamSet"
0x14005c0b6  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14005c0bb  jmp     loc_14005C332
0x14005c0c0  lea     rdx, [rbp+Environment]; Environment
0x14005c0c4  xor     ecx, ecx; Inherit
0x14005c0c6  xor     esi, esi
0x14005c0c8  call    cs:__imp_RtlCreateEnvironment
0x14005c0cf  nop     dword ptr [rax+rax+00h]
0x14005c0d4  test    eax, eax
0x14005c0d6  js      short loc_14005C0DC
0x14005c0d8  xor     eax, eax
0x14005c0da  jmp     short loc_14005C0F6
0x14005c0dc  mov     ecx, eax; Status
0x14005c0de  call    cs:__imp_RtlNtStatusToDosError
0x14005c0e5  nop     dword ptr [rax+rax+00h]
0x14005c0ea  test    eax, eax
0x14005c0ec  jle     short loc_14005C0F8
0x14005c0ee  movzx   eax, ax
0x14005c0f1  or      eax, 80070000h
0x14005c0f6  test    eax, eax
0x14005c0f8  jns     short loc_14005C102
0x14005c0fa  mov     r9d, 0C1h
0x14005c100  jmp     short loc_14005C09F
0x14005c102  cmp     [rbp+Environment], rsi
0x14005c106  jnz     short loc_14005C119
0x14005c108  mov     esi, 8000FFFFh
0x14005c10d  mov     r9d, 0C2h
0x14005c113  mov     dword ptr [rsp+60h+var_40], esi
0x14005c117  jmp     short loc_14005C0A3
0x14005c119  xor     ebx, ebx
0x14005c11b  lea     edi, [rbx+1]
0x14005c11e  cmp     ebx, [r12+8]
0x14005c123  jnb     loc_14005C216
0x14005c129  mov     rdx, [r12]
0x14005c12d  lea     rcx, [rbp+DestinationString]; DestinationString
0x14005c131  mov     r15d, ebx
0x14005c134  add     r15, r15
0x14005c137  mov     rdx, [rdx+r15*8]; SourceString
0x14005c13b  call    cs:__imp_RtlInitUnicodeStringEx
0x14005c142  nop     dword ptr [rax+rax+00h]
0x14005c147  test    eax, eax
0x14005c149  js      short loc_14005C14F
0x14005c14b  xor     eax, eax
0x14005c14d  jmp     short loc_14005C169
0x14005c14f  mov     ecx, eax; Status
0x14005c151  call    cs:__imp_RtlNtStatusToDosError
0x14005c158  nop     dword ptr [rax+rax+00h]
0x14005c15d  test    eax, eax
0x14005c15f  jle     short loc_14005C16B
0x14005c161  movzx   eax, ax
0x14005c164  or      eax, 80070000h
0x14005c169  test    eax, eax
0x14005c16b  js      loc_14005C205
0x14005c171  mov     rdx, [r12]
0x14005c175  lea     rcx, [rbp+Value]; DestinationString
0x14005c179  mov     rdx, [rdx+r15*8+8]; SourceString
0x14005c17e  call    cs:__imp_RtlInitUnicodeStringEx
0x14005c185  nop     dword ptr [rax+rax+00h]
0x14005c18a  test    eax, eax
0x14005c18c  js      short loc_14005C192
0x14005c18e  xor     eax, eax
0x14005c190  jmp     short loc_14005C1AC
0x14005c192  mov     ecx, eax; Status
0x14005c194  call    cs:__imp_RtlNtStatusToDosError
0x14005c19b  nop     dword ptr [rax+rax+00h]
0x14005c1a0  test    eax, eax
0x14005c1a2  jle     short loc_14005C1AE
0x14005c1a4  movzx   eax, ax
0x14005c1a7  or      eax, 80070000h
0x14005c1ac  test    eax, eax
0x14005c1ae  js      short loc_14005C1FD
0x14005c1b0  lea     r8, [rbp+Value]; Value
0x14005c1b4  lea     rdx, [rbp+DestinationString]; Name
0x14005c1b8  lea     rcx, [rbp+Environment]; Environment
0x14005c1bc  call    cs:__imp_RtlSetEnvironmentVariable
0x14005c1c3  nop     dword ptr [rax+rax+00h]
0x14005c1c8  test    eax, eax
0x14005c1ca  js      short loc_14005C1D0
0x14005c1cc  xor     eax, eax
0x14005c1ce  jmp     short loc_14005C1EA
0x14005c1d0  mov     ecx, eax; Status
0x14005c1d2  call    cs:__imp_RtlNtStatusToDosError
0x14005c1d9  nop     dword ptr [rax+rax+00h]
0x14005c1de  test    eax, eax
0x14005c1e0  jle     short loc_14005C1EC
0x14005c1e2  movzx   eax, ax
0x14005c1e5  or      eax, 80070000h
0x14005c1ea  test    eax, eax
0x14005c1ec  js      short loc_14005C1F5
0x14005c1ee  add     ebx, edi
0x14005c1f0  jmp     loc_14005C11E
0x14005c1f5  mov     r9d, 0D3h
0x14005c1fb  jmp     short loc_14005C20B
0x14005c1fd  mov     r9d, 0D0h
0x14005c203  jmp     short loc_14005C20B
0x14005c205  mov     r9d, 0CBh
0x14005c20b  mov     dword ptr [rsp+60h+var_40], eax
0x14005c20f  mov     ecx, edi
0x14005c211  jmp     loc_14005C0A8
0x14005c216  mov     r15d, 100000h
0x14005c21c  lea     r8, [rbp+var_30]; unsigned __int64 *
0x14005c220  mov     edx, r15d; unsigned __int64
0x14005c223  mov     rcx, r13; unsigned __int16 *
0x14005c226  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14005c22b  mov     esi, eax
0x14005c22d  test    eax, eax
0x14005c22f  jns     short loc_14005C239
0x14005c231  mov     r9d, 0D7h
0x14005c237  jmp     short loc_14005C20B
0x14005c239  mov     r8, [rbp+var_30]
0x14005c23d  lea     rax, [rbp+arg_18]
0x14005c241  mov     rcx, [rbp+Environment]
0x14005c245  xor     r9d, r9d
0x14005c248  mov     [rsp+60h+var_38], rax
0x14005c24d  mov     rdx, r13
0x14005c250  mov     [rsp+60h+var_40], r14
0x14005c255  call    cs:__imp_RtlExpandEnvironmentStrings
0x14005c25c  nop     dword ptr [rax+rax+00h]
0x14005c261  cmp     eax, 0C0000023h
0x14005c266  jnz     loc_14005C2F7
0x14005c26c  mov     rbx, [rbp+arg_18]
0x14005c270  cmp     rbx, r15
0x14005c273  jbe     short loc_14005C286
0x14005c275  mov     esi, 8007006Fh
0x14005c27a  mov     r9d, 0E7h
0x14005c280  mov     dword ptr [rsp+60h+var_40], esi
0x14005c284  jmp     short loc_14005C20F
0x14005c286  add     rbx, rbx
0x14005c289  call    cs:__imp_GetProcessHeap
0x14005c290  nop     dword ptr [rax+rax+00h]
0x14005c295  mov     r8, rbx; dwBytes
0x14005c298  xor     edx, edx; dwFlags
0x14005c29a  mov     rcx, rax; hHeap
0x14005c29d  call    cs:__imp_HeapAlloc
0x14005c2a4  nop     dword ptr [rax+rax+00h]
0x14005c2a9  mov     r14, rax
0x14005c2ac  test    rax, rax
0x14005c2af  jnz     short loc_14005C2C5
0x14005c2b1  mov     esi, 8007000Eh
0x14005c2b6  mov     r9d, 0EAh
0x14005c2bc  mov     dword ptr [rsp+60h+var_40], esi
0x14005c2c0  jmp     loc_14005C20F
0x14005c2c5  mov     r8, [rbp+var_30]
0x14005c2c9  xor     eax, eax
0x14005c2cb  mov     [r14], ax
0x14005c2cf  mov     r9, r14
0x14005c2d2  mov     rax, [rbp+arg_18]
0x14005c2d6  mov     rdx, r13
0x14005c2d9  mov     rcx, [rbp+Environment]
0x14005c2dd  mov     [rsp+60h+var_38], 0
0x14005c2e6  mov     [rsp+60h+var_40], rax
0x14005c2eb  call    cs:__imp_RtlExpandEnvironmentStrings
0x14005c2f2  nop     dword ptr [rax+rax+00h]
0x14005c2f7  test    eax, eax
0x14005c2f9  js      short loc_14005C2FF
0x14005c2fb  xor     eax, eax
0x14005c2fd  jmp     short loc_14005C319
0x14005c2ff  mov     ecx, eax; Status
0x14005c301  call    cs:__imp_RtlNtStatusToDosError
0x14005c308  nop     dword ptr [rax+rax+00h]
0x14005c30d  test    eax, eax
0x14005c30f  jle     short loc_14005C31B
0x14005c311  movzx   eax, ax
0x14005c314  or      eax, 80070000h
0x14005c319  test    eax, eax
0x14005c31b  jns     short loc_14005C328
0x14005c31d  mov     r9d, 0F6h
0x14005c323  jmp     loc_14005C20B
0x14005c328  mov     rax, [rbp+arg_0]
0x14005c32c  mov     [rax], r14
0x14005c32f  xor     r14d, r14d
0x14005c332  mov     rcx, [rbp+Environment]; Environment
0x14005c336  test    rcx, rcx
0x14005c339  jz      short loc_14005C347
0x14005c33b  call    cs:__imp_RtlDestroyEnvironment
0x14005c342  nop     dword ptr [rax+rax+00h]
0x14005c347  test    r14, r14
0x14005c34a  jz      short loc_14005C36C
0x14005c34c  call    cs:__imp_GetProcessHeap
0x14005c353  nop     dword ptr [rax+rax+00h]
0x14005c358  mov     r8, r14; lpMem
0x14005c35b  xor     edx, edx; dwFlags
0x14005c35d  mov     rcx, rax; hHeap
0x14005c360  call    cs:__imp_HeapFree
0x14005c367  nop     dword ptr [rax+rax+00h]
0x14005c36c  mov     rbx, [rsp+60h+arg_8]
0x14005c374  mov     eax, esi
0x14005c376  add     rsp, 60h
0x14005c37a  pop     r15
0x14005c37c  pop     r14
0x14005c37e  pop     r13
0x14005c380  pop     r12
0x14005c382  pop     rdi
0x14005c383  pop     rsi
0x14005c384  pop     rbp
0x14005c385  retn
```
