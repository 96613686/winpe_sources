# FwpmEventProviderFireNetEvent0

- ea: `0x180005070`
- end: `0x180005184`
- name: `FwpmEventProviderFireNetEvent0`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x1800034e0`
- `0x18000438c`
- `0x180005070`
- `0x1800052b0`
- `0x180005c4c`
- `0x180005f30`
- `0x180012bd0`
- `0x18001346a`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180005119`
- `ntdll!EtwEventWrite` at `0x180005119`
- `ntdll!EtwEventEnabled` at `0x1800050dd`
- `ntdll!EtwEventEnabled` at `0x1800050dd`

## string_xrefs

- `0x180005176`: `EtwEventWrite`

## pseudocode

```c
__int64 __fastcall FwpmEventProviderFireNetEvent0(_QWORD *a1, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 v5; // rbx
  int v8; // esi
  __int64 v9; // rcx
  unsigned int v10; // eax
  __int64 v11; // rcx
  __int64 result; // rax
  __int64 i; // rbx
  _QWORD v14[2]; // [rsp+20h] [rbp-1E8h] BYREF
  _DWORD v15[2]; // [rsp+30h] [rbp-1D8h] BYREF
  _BYTE v16[408]; // [rsp+38h] [rbp-1D0h] BYREF

  v5 = a4;
  v15[1] = 0;
  memset_0(v15, 0, 0x19Cu);
  v8 = 0;
  v9 = *a1;
  v14[0] = BFE_NET_EVENT_TYPES[2 * *(unsigned int *)(a2 + 136)];
  v14[1] = v5;
  if ( (unsigned __int8)EtwEventEnabled(v9, v14)
    && (BfeNetEventTrace(a2),
        BfeNetEventConvertToData(a2, v15),
        v8 = 1,
        (v10 = EtwEventWrite(*a1, v14, v15[0], v16)) != 0) )
  {
    WfpReportSysErrorAsWinError(v11, "EtwEventWrite", v10);
  }
  else
  {
    result = WfpWriteNeteventToUnifiedTrace(a2, a3);
    if ( !v8 )
      return result;
  }
  for ( i = 0; i != 2; ++i )
    result = WfpMemFree(&v16[8 * i + 392]);
  return result;
}

```

## disassembly

```asm
0x180005070  push    rbx
0x180005072  push    rbp
0x180005073  push    rsi
0x180005074  push    rdi
0x180005075  push    r14
0x180005077  sub     rsp, 1E0h
0x18000507e  mov     rax, cs:__security_cookie
0x180005085  xor     rax, rsp
0x180005088  mov     [rsp+208h+var_38], rax
0x180005090  mov     rbp, r8
0x180005093  mov     ebx, r9d
0x180005096  mov     rdi, rdx
0x180005099  mov     r14, rcx
0x18000509c  xor     eax, eax
0x18000509e  lea     rcx, [rsp+208h+var_1D8]; void *
0x1800050a3  xor     edx, edx; Val
0x1800050a5  mov     [rsp+208h+var_1D4], eax
0x1800050a9  mov     r8d, 19Ch; Size
0x1800050af  call    memset_0
0x1800050b4  mov     eax, [rdi+88h]
0x1800050ba  lea     rcx, BFE_NET_EVENT_TYPES
0x1800050c1  add     rax, rax
0x1800050c4  lea     rdx, [rsp+208h+var_1E8]
0x1800050c9  xor     esi, esi
0x1800050cb  movups  xmm0, xmmword ptr [rcx+rax*8]
0x1800050cf  mov     rcx, [r14]
0x1800050d2  movdqu  [rsp+208h+var_1E8], xmm0
0x1800050d8  mov     qword ptr [rsp+208h+var_1E8+8], rbx
0x1800050dd  call    cs:__imp_EtwEventEnabled
0x1800050e4  nop     dword ptr [rax+rax+00h]
0x1800050e9  test    al, al
0x1800050eb  jz      short loc_180005129
0x1800050ed  mov     rcx, rdi
0x1800050f0  call    BfeNetEventTrace
0x1800050f5  lea     rdx, [rsp+208h+var_1D8]
0x1800050fa  mov     rcx, rdi
0x1800050fd  call    BfeNetEventConvertToData
0x180005102  mov     r8d, [rsp+208h+var_1D8]
0x180005107  lea     r9, [rsp+208h+var_1D0]
0x18000510c  mov     rcx, [r14]
0x18000510f  lea     rdx, [rsp+208h+var_1E8]
0x180005114  mov     esi, 1
0x180005119  call    cs:__imp_EtwEventWrite
0x180005120  nop     dword ptr [rax+rax+00h]
0x180005125  test    eax, eax
0x180005127  jnz     short loc_180005173
0x180005129  mov     rdx, rbp
0x18000512c  mov     rcx, rdi
0x18000512f  call    WfpWriteNeteventToUnifiedTrace
0x180005134  test    esi, esi
0x180005136  jz      short loc_180005154
0x180005138  xor     ebx, ebx
0x18000513a  lea     rcx, [rsp+208h+var_48]
0x180005142  lea     rcx, [rcx+rbx*8]
0x180005146  call    WfpMemFree
0x18000514b  inc     rbx
0x18000514e  cmp     rbx, 2
0x180005152  jnz     short loc_18000513A
0x180005154  mov     rcx, [rsp+208h+var_38]
0x18000515c  xor     rcx, rsp; StackCookie
0x18000515f  call    __security_check_cookie
0x180005164  add     rsp, 1E0h
0x18000516b  pop     r14
0x18000516d  pop     rdi
0x18000516e  pop     rsi
0x18000516f  pop     rbp
0x180005170  pop     rbx
0x180005171  retn
0x180005173  mov     r8d, eax
0x180005176  lea     rdx, aEtweventwrite; "EtwEventWrite"
0x18000517d  call    WfpReportSysErrorAsWinError
0x180005182  jmp     short loc_180005138
```
