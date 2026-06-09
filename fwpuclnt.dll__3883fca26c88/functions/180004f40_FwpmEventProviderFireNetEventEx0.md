# FwpmEventProviderFireNetEventEx0

- ea: `0x180004f40`
- end: `0x180005066`
- name: `FwpmEventProviderFireNetEventEx0`
- size: `294`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x1800034e0`
- `0x18000438c`
- `0x180004f40`
- `0x1800052b0`
- `0x180005c4c`
- `0x180005f30`
- `0x180012bd0`
- `0x18001346a`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180004ffb`
- `ntdll!EtwEventWrite` at `0x180004ffb`
- `ntdll!EtwEventEnabled` at `0x180004fbf`
- `ntdll!EtwEventEnabled` at `0x180004fbf`

## string_xrefs

- `0x180005058`: `EtwEventWrite`

## pseudocode

```c
__int64 __fastcall FwpmEventProviderFireNetEventEx0(_QWORD *a1, __int64 a2, char a3, __int64 a4, unsigned int a5)
{
  int v9; // esi
  __int64 v10; // rcx
  unsigned int v11; // eax
  __int64 v12; // rcx
  __int64 result; // rax
  __int64 i; // rbx
  _QWORD v15[2]; // [rsp+20h] [rbp-1E8h] BYREF
  _DWORD v16[2]; // [rsp+30h] [rbp-1D8h] BYREF
  _BYTE v17[408]; // [rsp+38h] [rbp-1D0h] BYREF

  v16[1] = 0;
  memset_0(v16, 0, 0x19Cu);
  v9 = 0;
  v10 = *a1;
  v15[0] = BFE_NET_EVENT_TYPES[2 * (*(_DWORD *)(a2 + 136) - (a3 != 0 ? 0xD : 0))];
  v15[1] = a5;
  if ( (unsigned __int8)EtwEventEnabled(v10, v15)
    && (BfeNetEventTrace(a2),
        BfeNetEventConvertToData(a2, v16),
        v9 = 1,
        (v11 = EtwEventWrite(*a1, v15, v16[0], v17)) != 0) )
  {
    WfpReportSysErrorAsWinError(v12, "EtwEventWrite", v11);
  }
  else
  {
    result = WfpWriteNeteventToUnifiedTrace(a2, a4);
    if ( !v9 )
      return result;
  }
  for ( i = 0; i != 2; ++i )
    result = WfpMemFree(&v17[8 * i + 392]);
  return result;
}

```

## disassembly

```asm
0x180004f40  push    rbx
0x180004f42  push    rbp
0x180004f43  push    rsi
0x180004f44  push    rdi
0x180004f45  push    r14
0x180004f47  sub     rsp, 1E0h
0x180004f4e  mov     rax, cs:__security_cookie
0x180004f55  xor     rax, rsp
0x180004f58  mov     [rsp+208h+var_38], rax
0x180004f60  mov     bl, r8b
0x180004f63  mov     rdi, rdx
0x180004f66  mov     r14, rcx
0x180004f69  xor     eax, eax
0x180004f6b  xor     edx, edx; Val
0x180004f6d  mov     [rsp+208h+var_1D4], eax
0x180004f71  mov     r8d, 19Ch; Size
0x180004f77  lea     rcx, [rsp+208h+var_1D8]; void *
0x180004f7c  mov     rbp, r9
0x180004f7f  call    memset_0
0x180004f84  mov     eax, [rdi+88h]
0x180004f8a  lea     rdx, [rsp+208h+var_1E8]
0x180004f8f  xor     esi, esi
0x180004f91  neg     bl
0x180004f93  sbb     ecx, ecx
0x180004f95  and     ecx, 0Dh
0x180004f98  sub     eax, ecx
0x180004f9a  mov     ecx, eax
0x180004f9c  lea     rax, BFE_NET_EVENT_TYPES
0x180004fa3  add     rcx, rcx
0x180004fa6  movups  xmm0, xmmword ptr [rax+rcx*8]
0x180004faa  mov     eax, [rsp+208h+arg_20]
0x180004fb1  mov     rcx, [r14]
0x180004fb4  movdqu  [rsp+208h+var_1E8], xmm0
0x180004fba  mov     qword ptr [rsp+208h+var_1E8+8], rax
0x180004fbf  call    cs:__imp_EtwEventEnabled
0x180004fc6  nop     dword ptr [rax+rax+00h]
0x180004fcb  test    al, al
0x180004fcd  jz      short loc_18000500B
0x180004fcf  mov     rcx, rdi
0x180004fd2  call    BfeNetEventTrace
0x180004fd7  lea     rdx, [rsp+208h+var_1D8]
0x180004fdc  mov     rcx, rdi
0x180004fdf  call    BfeNetEventConvertToData
0x180004fe4  mov     r8d, [rsp+208h+var_1D8]
0x180004fe9  lea     r9, [rsp+208h+var_1D0]
0x180004fee  mov     rcx, [r14]
0x180004ff1  lea     rdx, [rsp+208h+var_1E8]
0x180004ff6  mov     esi, 1
0x180004ffb  call    cs:__imp_EtwEventWrite
0x180005002  nop     dword ptr [rax+rax+00h]
0x180005007  test    eax, eax
0x180005009  jnz     short loc_180005055
0x18000500b  mov     rdx, rbp
0x18000500e  mov     rcx, rdi
0x180005011  call    WfpWriteNeteventToUnifiedTrace
0x180005016  test    esi, esi
0x180005018  jz      short loc_180005036
0x18000501a  xor     ebx, ebx
0x18000501c  lea     rcx, [rsp+208h+var_48]
0x180005024  lea     rcx, [rcx+rbx*8]
0x180005028  call    WfpMemFree
0x18000502d  inc     rbx
0x180005030  cmp     rbx, 2
0x180005034  jnz     short loc_18000501C
0x180005036  mov     rcx, [rsp+208h+var_38]
0x18000503e  xor     rcx, rsp; StackCookie
0x180005041  call    __security_check_cookie
0x180005046  add     rsp, 1E0h
0x18000504d  pop     r14
0x18000504f  pop     rdi
0x180005050  pop     rsi
0x180005051  pop     rbp
0x180005052  pop     rbx
0x180005053  retn
0x180005055  mov     r8d, eax
0x180005058  lea     rdx, aEtweventwrite; "EtwEventWrite"
0x18000505f  call    WfpReportSysErrorAsWinError
0x180005064  jmp     short loc_18000501A
```
