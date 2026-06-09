# AllocateSecurityDescriptorAllowAccessToWorld(void * *,_AdvapiLinkageStruct *)

- ea: `0x180002144`
- end: `0x1800022ff`
- name: `?AllocateSecurityDescriptorAllowAccessToWorld@@YAKPEAPEAXPEAU_AdvapiLinkageStruct@@@Z`
- size: `443`
- prototype: `unsigned int __fastcall(void **, struct _AdvapiLinkageStruct *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002310`

## callees

- `0x180002144`
- `0x180004e1c`
- `0x1800054b0`
- `0x180006010`

## import_xrefs

- `cmutil!CmFree` at `0x1800022b5`
- `cmutil!CmFree` at `0x1800022b5`
- `cmutil!CmMalloc` at `0x1800021ae`
- `cmutil!CmMalloc` at `0x1800021ae`
- `KERNEL32!GetLastError` at `0x1800022a6`
- `KERNEL32!GetLastError` at `0x1800022a6`

## string_xrefs

- `0x1800022ca`: `AllocateSecurityDescriptorAllowAccessToWorld() - Arithmetic operation failed: %ld\n`

## pseudocode

```c
__int64 __fastcall AllocateSecurityDescriptorAllowAccessToWorld(void **a1, __int64 (__fastcall **a2)(void **))
{
  void **v3; // r15
  unsigned int v5; // eax
  __int64 v6; // r9
  unsigned int v7; // r14d
  unsigned int v8; // ecx
  DWORD LastError; // ebx
  char *v10; // rax
  __int64 v11; // r8
  char *v12; // rdi
  char *v13; // rbx
  __int64 (__fastcall *v14)(void **); // rax
  int v15; // [rsp+30h] [rbp-38h] BYREF
  __int16 v16; // [rsp+34h] [rbp-34h]

  v3 = a1;
  if ( !a1 )
    return 87;
  *a1 = 0;
  LOBYTE(a1) = 1;
  v5 = a2[1](a1);
  v7 = (v5 + 27) & 0xFFFFFFF8;
  v8 = v7 + v5;
  if ( v7 + v5 < v5 || v8 + 40 < v8 )
  {
    MyDbgPrintfW(
      0xFFFFFFFFLL,
      L"AllocateSecurityDescriptorAllowAccessToWorld() - Arithmetic operation failed: %ld\n",
      2147942934LL,
      v6);
    return 534;
  }
  else
  {
    LastError = 14;
    v10 = (char *)CmMalloc(v8 + 40);
    v12 = v10;
    if ( v10 )
    {
      v13 = v10 + 40;
      v14 = a2[2];
      v15 = 0;
      v16 = 256;
      LOBYTE(v11) = 1;
      if ( ((unsigned int (__fastcall *)(char *, int *, __int64))v14)(&v13[v7], &v15, v11)
        && (*(_DWORD *)((__int64 (__fastcall *)(char *, _QWORD))a2[3])(&v13[v7], 0) = 0,
            ((unsigned int (__fastcall *)(char *, _QWORD, __int64))a2[4])(v13, v7, 2))
        && ((unsigned int (__fastcall *)(char *, __int64, __int64, __int64, char *))a2[5])(v13, 2, 3, 1310719, &v13[v7])
        && ((unsigned int (__fastcall *)(char *, __int64))a2[6])(v12, 1)
        && ((unsigned int (__fastcall *)(char *, __int64, char *))a2[7])(v12, 1, v13)
        && ((unsigned int (__fastcall *)(char *, _QWORD, __int64))a2[8])(v12, 0, 1)
        && (LastError = 0, ((unsigned int (__fastcall *)(char *, _QWORD, _QWORD))a2[9])(v12, 0, 0))
        || (LastError = GetLastError()) == 0 )
      {
        *v3 = v12;
      }
      else
      {
        CmFree(v12);
      }
    }
    return LastError;
  }
}

```

## disassembly

```asm
0x180002144  mov     [rsp+arg_10], rbx
0x180002149  push    rbp
0x18000214a  push    rsi
0x18000214b  push    rdi
0x18000214c  push    r14
0x18000214e  push    r15
0x180002150  sub     rsp, 40h
0x180002154  mov     rax, cs:__security_cookie
0x18000215b  xor     rax, rsp
0x18000215e  mov     [rsp+68h+var_30], rax
0x180002163  mov     rsi, rdx
0x180002166  mov     r15, rcx
0x180002169  test    rcx, rcx
0x18000216c  jnz     short loc_180002176
0x18000216e  lea     eax, [rcx+57h]
0x180002171  jmp     loc_1800022DE
0x180002176  mov     qword ptr [rcx], 0
0x18000217d  mov     cl, 1
0x18000217f  mov     rax, [rdx+8]
0x180002183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002188  lea     r14d, [rax+1Bh]
0x18000218c  and     r14d, 0FFFFFFF8h
0x180002190  lea     ecx, [r14+rax]
0x180002194  cmp     ecx, eax
0x180002196  jb      loc_1800022C4
0x18000219c  lea     eax, [rcx+28h]
0x18000219f  cmp     eax, ecx
0x1800021a1  jb      loc_1800022C4
0x1800021a7  mov     ecx, eax
0x1800021a9  mov     ebx, 0Eh
0x1800021ae  call    cs:__imp_?CmMalloc@@YAPEAX_K@Z; CmMalloc(unsigned __int64)
0x1800021b4  mov     rdi, rax
0x1800021b7  test    rax, rax
0x1800021ba  jz      loc_1800022C0
0x1800021c0  lea     rbx, [rax+28h]
0x1800021c4  mov     ebp, r14d
0x1800021c7  mov     rax, [rsi+10h]
0x1800021cb  lea     rdx, [rsp+68h+var_38]
0x1800021d0  add     rbp, rbx
0x1800021d3  mov     [rsp+68h+var_38], 0
0x1800021db  mov     rcx, rbp
0x1800021de  mov     [rsp+68h+var_34], 100h
0x1800021e5  mov     r8b, 1
0x1800021e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021ed  test    eax, eax
0x1800021ef  jz      loc_1800022A6
0x1800021f5  mov     rax, [rsi+18h]
0x1800021f9  xor     edx, edx
0x1800021fb  mov     rcx, rbp
0x1800021fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002203  mov     r8d, 2
0x180002209  mov     edx, r14d
0x18000220c  mov     rcx, rbx
0x18000220f  mov     dword ptr [rax], 0
0x180002215  mov     rax, [rsi+20h]
0x180002219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000221e  test    eax, eax
0x180002220  jz      loc_1800022A6
0x180002226  mov     rax, [rsi+28h]
0x18000222a  mov     edx, 2
0x18000222f  mov     r9d, 13FFFFh
0x180002235  mov     [rsp+68h+var_48], rbp
0x18000223a  mov     rcx, rbx
0x18000223d  lea     r8d, [rdx+1]
0x180002241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002246  test    eax, eax
0x180002248  jz      short loc_1800022A6
0x18000224a  mov     rax, [rsi+30h]
0x18000224e  mov     edx, 1
0x180002253  mov     rcx, rdi
0x180002256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000225b  test    eax, eax
0x18000225d  jz      short loc_1800022A6
0x18000225f  mov     rax, [rsi+38h]
0x180002263  xor     r9d, r9d
0x180002266  mov     r8, rbx
0x180002269  mov     rcx, rdi
0x18000226c  lea     edx, [r9+1]
0x180002270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002275  test    eax, eax
0x180002277  jz      short loc_1800022A6
0x180002279  mov     rax, [rsi+40h]
0x18000227d  xor     edx, edx
0x18000227f  mov     rcx, rdi
0x180002282  lea     r8d, [rdx+1]
0x180002286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000228b  test    eax, eax
0x18000228d  jz      short loc_1800022A6
0x18000228f  mov     rax, [rsi+48h]
0x180002293  xor     r8d, r8d
0x180002296  xor     edx, edx
0x180002298  mov     rcx, rdi
0x18000229b  xor     ebx, ebx
0x18000229d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022a2  test    eax, eax
0x1800022a4  jnz     short loc_1800022BD
0x1800022a6  call    cs:__imp_GetLastError
0x1800022ac  mov     ebx, eax
0x1800022ae  test    eax, eax
0x1800022b0  jz      short loc_1800022BD
0x1800022b2  mov     rcx, rdi
0x1800022b5  call    cs:__imp_?CmFree@@YAXPEAX@Z; CmFree(void *)
0x1800022bb  jmp     short loc_1800022C0
0x1800022bd  mov     [r15], rdi
0x1800022c0  mov     eax, ebx
0x1800022c2  jmp     short loc_1800022DE
0x1800022c4  mov     r8d, 80070216h
0x1800022ca  lea     rdx, aAllocatesecuri; "AllocateSecurityDescriptorAllowAccessTo"...
0x1800022d1  or      ecx, 0FFFFFFFFh
0x1800022d4  call    MyDbgPrintfW
0x1800022d9  mov     eax, 216h
0x1800022de  mov     rcx, [rsp+68h+var_30]
0x1800022e3  xor     rcx, rsp; StackCookie
0x1800022e6  call    __security_check_cookie
0x1800022eb  mov     rbx, [rsp+68h+arg_10]
0x1800022f3  add     rsp, 40h
0x1800022f7  pop     r15
0x1800022f9  pop     r14
0x1800022fb  pop     rdi
0x1800022fc  pop     rsi
0x1800022fd  pop     rbp
0x1800022fe  retn
```
