# StatByPath64

- ea: `0x18000990c`
- end: `0x180009afb`
- name: `StatByPath64`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180009b10`

## callees

- `0x180004cb0`
- `0x180008330`
- `0x180009684`
- `0x180009844`
- `0x18000990c`
- `0x180079760`
- `0x1800798c0`
- `0x18007d030`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000997a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000998c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000997a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000998c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800099a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800099a1`

## string_xrefs

- `0x180009985`: `kernel32.dll`
- `0x180009973`: `kernelbase.dll`

## pseudocode

```c
__int64 __fastcall StatByPath64(wint_t *a1, __int64 a2)
{
  FARPROC ProcAddress; // rdi
  unsigned int v5; // r15d
  HMODULE ModuleHandleW; // rax
  __int64 v7; // rax
  int v8; // edi
  __int64 v9; // rcx
  __int16 v10; // ax
  __int64 v11; // rcx
  __int16 v12; // ax
  __int64 v14; // [rsp+30h] [rbp-69h] BYREF
  _BYTE v15[8]; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v16[8]; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v17[8]; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v18[24]; // [rsp+58h] [rbp-41h] BYREF
  unsigned int v19; // [rsp+70h] [rbp-29h]
  int v20; // [rsp+74h] [rbp-25h]
  unsigned int v21; // [rsp+78h] [rbp-21h]
  unsigned int v22; // [rsp+80h] [rbp-19h]
  int v23; // [rsp+84h] [rbp-15h]

  memset_thunk_772440563353939046(v15, 0, 0x68u);
  ProcAddress = (FARPROC)`DoGetFileInformationByName'::`2'::cachedQueryFunction;
  v14 = 0;
  v5 = 0;
  if ( `DoGetFileInformationByName'::`2'::cachedQueryFunction != -1 )
  {
    if ( `DoGetFileInformationByName'::`2'::cachedQueryFunction )
      goto LABEL_11;
    ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
    if ( ModuleHandleW || (ModuleHandleW = GetModuleHandleW(L"kernel32.dll")) != 0 )
      ProcAddress = GetProcAddress(ModuleHandleW, "GetFileInformationByName");
    v7 = -1;
    if ( ProcAddress )
      v7 = (__int64)ProcAddress;
    `DoGetFileInformationByName'::`2'::cachedQueryFunction = v7;
    if ( ProcAddress )
    {
LABEL_11:
      if ( ((unsigned int (__fastcall *)(wint_t *, __int64, _BYTE *, __int64))ProcAddress)(a1, 3, v15, 104)
        && ((unsigned int)(v23 - 7) <= 1 || v23 == 36) )
      {
        *(_OWORD *)a2 = 0;
        *(_OWORD *)(a2 + 16) = 0;
        *(_OWORD *)(a2 + 32) = 0;
        *(_QWORD *)(a2 + 48) = 0;
        if ( *a1 )
        {
          if ( a1[1] == 58 )
          {
            if ( !a1[2] )
              return v5;
            v8 = towlower(*a1) - 96;
          }
          else
          {
            v8 = getdrive();
          }
          if ( (unsigned int)MapFileInfoTime64(v18, &v14, a2 + 40)
            && (unsigned int)MapFileInfoTime64(v17, a2 + 40, a2 + 32)
            && (unsigned int)MapFileInfoTime64(v16, a2 + 40, a2 + 48) )
          {
            v9 = v21;
            *(_DWORD *)a2 = v8 - 1;
            *(_DWORD *)(a2 + 16) = v8 - 1;
            v10 = _wdtoxmode(v9, a1);
            v11 = v20;
            v5 = 1;
            *(_WORD *)(a2 + 6) = v10;
            v12 = v22;
            if ( v22 > 0xFFFF )
              v12 = -1;
            *(_WORD *)(a2 + 8) = v12;
            *(_QWORD *)(a2 + 24) = v19 + (v11 << 32);
          }
          else
          {
            *(_OWORD *)a2 = 0;
            *(_OWORD *)(a2 + 16) = 0;
            *(_OWORD *)(a2 + 32) = 0;
            *(_QWORD *)(a2 + 48) = 0;
          }
        }
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000990c  mov     [rsp-8+arg_10], rbx
0x180009911  push    rbp
0x180009912  push    rsi
0x180009913  push    rdi
0x180009914  push    r12
0x180009916  push    r13
0x180009918  push    r14
0x18000991a  push    r15
0x18000991c  lea     rbp, [rsp-27h]
0x180009921  sub     rsp, 0C0h
0x180009928  mov     rax, cs:__security_cookie
0x18000992f  xor     rax, rsp
0x180009932  mov     [rbp+57h+var_40], rax
0x180009936  mov     rbx, rdx
0x180009939  mov     rsi, rcx
0x18000993c  mov     r14d, 68h ; 'h'
0x180009942  lea     rcx, [rbp+57h+var_B0]; void *
0x180009946  mov     r8d, r14d; Size
0x180009949  xor     edx, edx; Val
0x18000994b  call    memset$thunk$772440563353939046
0x180009950  mov     rdi, cs:?cachedQueryFunction@?1??DoGetFileInformationByName@@9@9; `DoGetFileInformationByName'::`2'::cachedQueryFunction
0x180009957  xor     r12d, r12d
0x18000995a  or      r13, 0FFFFFFFFFFFFFFFFh
0x18000995e  mov     [rbp+57h+var_C0], r12
0x180009962  mov     r15d, r12d
0x180009965  cmp     rdi, r13
0x180009968  jz      loc_180009AD1
0x18000996e  test    rdi, rdi
0x180009971  jnz     short loc_1800099C1
0x180009973  lea     rcx, aKernelbaseDll_0; "kernelbase.dll"
0x18000997a  call    cs:__imp_GetModuleHandleW
0x180009980  test    rax, rax
0x180009983  jnz     short loc_180009997
0x180009985  lea     rcx, ModuleName; "kernel32.dll"
0x18000998c  call    cs:__imp_GetModuleHandleW
0x180009992  test    rax, rax
0x180009995  jz      short loc_1800099AA
0x180009997  lea     rdx, aGetfileinforma; "GetFileInformationByName"
0x18000999e  mov     rcx, rax; hModule
0x1800099a1  call    cs:__imp_GetProcAddress
0x1800099a7  mov     rdi, rax
0x1800099aa  test    rdi, rdi
0x1800099ad  mov     rax, r13
0x1800099b0  cmovnz  rax, rdi
0x1800099b4  mov     cs:?cachedQueryFunction@?1??DoGetFileInformationByName@@9@9, rax; `DoGetFileInformationByName'::`2'::cachedQueryFunction
0x1800099bb  jz      loc_180009AD1
0x1800099c1  mov     r9d, r14d
0x1800099c4  lea     r8, [rbp+57h+var_B0]
0x1800099c8  mov     edx, 3
0x1800099cd  mov     rcx, rsi
0x1800099d0  mov     rax, rdi
0x1800099d3  call    cs:__guard_dispatch_icall_fptr
0x1800099d9  test    eax, eax
0x1800099db  jz      loc_180009AD1
0x1800099e1  mov     ecx, [rbp+57h+var_6C]
0x1800099e4  lea     eax, [rcx-7]
0x1800099e7  cmp     eax, 1
0x1800099ea  jbe     short loc_1800099F5
0x1800099ec  cmp     ecx, 24h ; '$'
0x1800099ef  jnz     loc_180009AD1
0x1800099f5  xorps   xmm0, xmm0
0x1800099f8  xor     eax, eax
0x1800099fa  movups  xmmword ptr [rbx], xmm0
0x1800099fd  movups  xmmword ptr [rbx+10h], xmm0
0x180009a01  movups  xmmword ptr [rbx+20h], xmm0
0x180009a05  mov     [rbx+30h], rax
0x180009a09  movzx   ecx, word ptr [rsi]; C
0x180009a0c  test    cx, cx
0x180009a0f  jz      loc_180009AD1
0x180009a15  cmp     word ptr [rsi+2], 3Ah ; ':'
0x180009a1a  jz      short loc_180009A25
0x180009a1c  call    _getdrive
0x180009a21  mov     edi, eax
0x180009a23  jmp     short loc_180009A3B
0x180009a25  cmp     [rsi+4], r12w
0x180009a2a  jz      loc_180009AD1
0x180009a30  call    towlower
0x180009a35  movzx   edi, ax
0x180009a38  sub     edi, 60h ; '`'
0x180009a3b  lea     r14, [rbx+28h]
0x180009a3f  mov     r8, r14
0x180009a42  lea     rdx, [rbp+57h+var_C0]
0x180009a46  lea     rcx, [rbp+57h+var_98]
0x180009a4a  call    MapFileInfoTime64
0x180009a4f  test    eax, eax
0x180009a51  jz      short loc_180009ABD
0x180009a53  lea     r8, [rbx+20h]
0x180009a57  mov     rdx, r14
0x180009a5a  lea     rcx, [rbp+57h+var_A0]
0x180009a5e  call    MapFileInfoTime64
0x180009a63  test    eax, eax
0x180009a65  jz      short loc_180009ABD
0x180009a67  lea     r8, [rbx+30h]
0x180009a6b  mov     rdx, r14
0x180009a6e  lea     rcx, [rbp+57h+var_A8]
0x180009a72  call    MapFileInfoTime64
0x180009a77  test    eax, eax
0x180009a79  jz      short loc_180009ABD
0x180009a7b  mov     ecx, [rbp+57h+var_78]
0x180009a7e  lea     eax, [rdi-1]
0x180009a81  mov     rdx, rsi
0x180009a84  mov     [rbx], eax
0x180009a86  mov     [rbx+10h], eax
0x180009a89  call    __wdtoxmode
0x180009a8e  movsxd  rcx, [rbp+57h+var_7C]
0x180009a92  mov     r15d, 1
0x180009a98  mov     [rbx+6], ax
0x180009a9c  mov     eax, [rbp+57h+var_70]
0x180009a9f  cmp     eax, 0FFFFh
0x180009aa4  cmova   ax, r13w
0x180009aa9  shl     rcx, 20h
0x180009aad  mov     [rbx+8], ax
0x180009ab1  mov     eax, [rbp+57h+var_80]
0x180009ab4  add     rcx, rax
0x180009ab7  mov     [rbx+18h], rcx
0x180009abb  jmp     short loc_180009AD1
0x180009abd  xorps   xmm0, xmm0
0x180009ac0  xor     eax, eax
0x180009ac2  movups  xmmword ptr [rbx], xmm0
0x180009ac5  movups  xmmword ptr [rbx+10h], xmm0
0x180009ac9  movups  xmmword ptr [rbx+20h], xmm0
0x180009acd  mov     [rbx+30h], rax
0x180009ad1  mov     eax, r15d
0x180009ad4  mov     rcx, [rbp+57h+var_40]
0x180009ad8  xor     rcx, rsp; StackCookie
0x180009adb  call    __security_check_cookie
0x180009ae0  mov     rbx, [rsp+0F0h+arg_10]
0x180009ae8  add     rsp, 0C0h
0x180009aef  pop     r15
0x180009af1  pop     r14
0x180009af3  pop     r13
0x180009af5  pop     r12
0x180009af7  pop     rdi
0x180009af8  pop     rsi
0x180009af9  pop     rbp
0x180009afa  retn
```
