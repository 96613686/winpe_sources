# Configuration::DeSerialize(IRegWrapper::Key *)

- ea: `0x18000c26c`
- end: `0x18000c586`
- name: `?DeSerialize@Configuration@@QEAAXPEAVKey@IRegWrapper@@@Z`
- size: `794`
- prototype: `void __fastcall(Configuration *__hidden this, struct IRegWrapper::Key *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x18000c934`

## callees

- `0x18000b218`
- `0x18000bf68`
- `0x18000c26c`
- `0x1800304ec`
- `0x180030568`
- `0x180030ab8`
- `0x180030d84`
- `0x180034fd4`
- `0x18003dc30`
- `0x18003dc50`
- `0x18003f280`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000c54a`
- `KERNEL32!HeapFree` at `0x18000c54a`
- `KERNEL32!GetProcessHeap` at `0x18000c535`
- `KERNEL32!GetProcessHeap` at `0x18000c535`

## string_xrefs

- `0x18000c328`: `Config`

## pseudocode

```c
void __fastcall Configuration::DeSerialize(Configuration *this, struct IRegWrapper::Key *a2)
{
  _DWORD *v4; // r15
  _DWORD *v5; // rdi
  const unsigned __int16 *v6; // rdx
  __int64 v7; // r14
  _DWORD *v8; // rdi
  bool v9; // al
  void *v10; // rbx
  HANDLE ProcessHeap; // rax
  int v12; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD *v13; // [rsp+28h] [rbp-D8h]
  _DWORD *v14; // [rsp+30h] [rbp-D0h]
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+44h] [rbp-BCh]
  LPVOID lpMem; // [rsp+50h] [rbp-B0h]
  __int16 v18; // [rsp+58h] [rbp-A8h] BYREF

  v4 = (_DWORD *)((char *)this + 16);
  if ( !(*(unsigned __int8 (__fastcall **)(struct IRegWrapper::Key *, const wchar_t *, char *))(*(_QWORD *)a2 + 48LL))(
          a2,
          L"Status",
          (char *)this + 16) )
    *v4 = 0;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IRegWrapper::Key *, const wchar_t *, char *))(*(_QWORD *)a2 + 48LL))(
          a2,
          L"Scenario",
          (char *)this + 24) )
  {
    *((_DWORD *)this + 6) = 0;
    *v4 = 0;
  }
  v16 = 512;
  lpMem = &v18;
  v15 = 2;
  v18 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(struct IRegWrapper::Key *, const wchar_t *, int *))(*(_QWORD *)a2 + 40LL))(
         a2,
         L"Config",
         &v15) )
  {
    v5 = operator new(0x18u);
    v14 = v5;
    if ( v5 )
    {
      SString::ConvertToUnicode((SString *)&v15);
      v6 = (const unsigned __int16 *)lpMem;
      v13 = v5;
      *v5 = 2;
      v5[1] = 2;
      v5[2] = 16;
      *((_QWORD *)v5 + 2) = &SString::s_EmptyBuffer;
      if ( !v6 )
        ThrowHR(-2147024736);
      Image::DeSerialize((Image *)v5, v6);
    }
    else
    {
      v5 = 0;
    }
    if ( *((_DWORD *)this + 144) )
    {
      v7 = *((_QWORD *)this + 71);
      v13 = (_DWORD *)v7;
      if ( v7 )
      {
        v13 = (_DWORD *)v7;
        if ( (*(_BYTE *)(v7 + 8) & 8) != 0 )
          operator delete(*(void **)(v7 + 16));
        operator delete((void *)v7);
      }
      *((_DWORD *)this + 144) = 0;
    }
    *((_QWORD *)this + 71) = v5;
    if ( v5 )
      *((_DWORD *)this + 144) = 1;
  }
  (*(void (__fastcall **)(struct IRegWrapper::Key *, const wchar_t *, char *))(*(_QWORD *)a2 + 40LL))(
    a2,
    L"RepositoryDir",
    (char *)this + 584);
  if ( !(*(unsigned __int8 (__fastcall **)(struct IRegWrapper::Key *, const wchar_t *, char *))(*(_QWORD *)a2 + 48LL))(
          a2,
          L"RepositoryFlags",
          (char *)this + 608) )
    *((_DWORD *)this + 152) = 0;
  Configuration::BinaryDeSerializeLogicalImageList(this, a2);
  v8 = (_DWORD *)((char *)this + 648);
  if ( !(*(unsigned __int8 (__fastcall **)(struct IRegWrapper::Key *, const wchar_t *, char *))(*(_QWORD *)a2 + 48LL))(
          a2,
          L"RuntimeMissing",
          (char *)this + 648) )
    *v8 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(struct IRegWrapper::Key *, const wchar_t *, int *))(*(_QWORD *)a2 + 48LL))(
         a2,
         L"KeepRuntimeVersion",
         &v12) )
  {
    v9 = v12 != 0;
    *((_BYTE *)this + 640) = v12 != 0;
    if ( v9 )
      goto LABEL_34;
  }
  else
  {
    *((_BYTE *)this + 640) = 0;
  }
  if ( *v4 == 2 )
  {
    if ( (*((_DWORD *)this + 8) & 0xFFFFFFF8) == 0 )
      goto LABEL_36;
  }
  else if ( *v4 != 3 && (*v4 || (*((_DWORD *)this + 8) & 0xFFFFFFF8) == 0) && (*v4 != 5 || *v8) )
  {
    goto LABEL_36;
  }
LABEL_34:
  if ( !(*(unsigned __int8 (__fastcall **)(struct IRegWrapper::Key *, const wchar_t *, char *))(*(_QWORD *)a2 + 40LL))(
          a2,
          L"RuntimeVersion",
          (char *)this + 616) )
    SString::Set((Configuration *)((char *)this + 616), L"v2.0.50727");
LABEL_36:
  if ( (v16 & 0x800000000LL) != 0 )
  {
    v10 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v10);
    }
  }
}

```

## disassembly

```asm
0x18000c26c  mov     [rsp-8+arg_10], rbx
0x18000c271  mov     [rsp-8+arg_18], rsi
0x18000c276  push    rbp
0x18000c277  push    rdi
0x18000c278  push    r12
0x18000c27a  push    r14
0x18000c27c  push    r15
0x18000c27e  lea     rbp, [rsp-170h]
0x18000c286  sub     rsp, 270h
0x18000c28d  mov     rax, cs:__security_cookie
0x18000c294  xor     rax, rsp
0x18000c297  mov     [rbp+190h+var_30], rax
0x18000c29e  mov     rsi, rdx
0x18000c2a1  mov     rbx, rcx
0x18000c2a4  lea     r15, [rcx+10h]
0x18000c2a8  mov     rax, [rdx]
0x18000c2ab  mov     r8, r15
0x18000c2ae  lea     rdx, aStatus_0; "Status"
0x18000c2b5  mov     rcx, rsi
0x18000c2b8  mov     rax, [rax+30h]
0x18000c2bc  call    cs:__guard_dispatch_icall_fptr
0x18000c2c2  xor     r12d, r12d
0x18000c2c5  test    al, al
0x18000c2c7  jnz     short loc_18000C2CC
0x18000c2c9  mov     [r15], r12d
0x18000c2cc  mov     rax, [rsi]
0x18000c2cf  lea     r8, [rbx+18h]
0x18000c2d3  lea     rdx, aScenario; "Scenario"
0x18000c2da  mov     rcx, rsi
0x18000c2dd  mov     rax, [rax+30h]
0x18000c2e1  call    cs:__guard_dispatch_icall_fptr
0x18000c2e7  test    al, al
0x18000c2e9  jnz     short loc_18000C2F2
0x18000c2eb  mov     [rbx+18h], r12d
0x18000c2ef  mov     [r15], r12d
0x18000c2f2  mov     [rsp+290h+var_250], r12
0x18000c2f7  mov     [rsp+290h+var_250+4], 200h
0x18000c300  mov     [rsp+290h+lpMem], r12
0x18000c305  lea     rax, [rsp+290h+var_238]
0x18000c30a  mov     [rsp+290h+lpMem], rax
0x18000c30f  mov     dword ptr [rsp+290h+var_250], 2
0x18000c317  mov     rax, [rsp+290h+lpMem]
0x18000c31c  mov     [rax], r12w
0x18000c320  mov     rax, [rsi]
0x18000c323  lea     r8, [rsp+290h+var_250]
0x18000c328  lea     rdx, aConfig; "Config"
0x18000c32f  mov     rcx, rsi
0x18000c332  mov     rax, [rax+28h]
0x18000c336  call    cs:__guard_dispatch_icall_fptr
0x18000c33c  test    al, al
0x18000c33e  jz      loc_18000C3FE
0x18000c344  mov     ecx, 18h; dwBytes
0x18000c349  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c34e  mov     rdi, rax
0x18000c351  mov     [rsp+290h+var_260], rax
0x18000c356  test    rax, rax
0x18000c359  jz      short loc_18000C3A2
0x18000c35b  lea     rcx, [rsp+290h+var_250]; this
0x18000c360  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18000c365  mov     rdx, [rsp+290h+lpMem]; unsigned __int16 *
0x18000c36a  mov     [rsp+290h+var_268], rdi
0x18000c36f  mov     dword ptr [rdi], 2
0x18000c375  mov     dword ptr [rdi+4], 2
0x18000c37c  mov     dword ptr [rdi+8], 10h
0x18000c383  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x18000c38a  mov     [rdi+10h], rax
0x18000c38e  test    rdx, rdx
0x18000c391  jz      loc_18000C57B
0x18000c397  mov     rcx, rdi; this
0x18000c39a  call    ?DeSerialize@Image@@QEAAXPEBG@Z; Image::DeSerialize(ushort const *)
0x18000c39f  nop
0x18000c3a0  jmp     short loc_18000C3A5
0x18000c3a2  mov     rdi, r12
0x18000c3a5  cmp     [rbx+240h], r12d
0x18000c3ac  jz      short loc_18000C3E8
0x18000c3ae  mov     r14, [rbx+238h]
0x18000c3b5  mov     [rsp+290h+var_268], r14
0x18000c3ba  test    r14, r14
0x18000c3bd  jz      short loc_18000C3E1
0x18000c3bf  mov     [rsp+290h+var_268], r14
0x18000c3c4  test    byte ptr [r14+8], 8
0x18000c3c9  jz      short loc_18000C3D4
0x18000c3cb  mov     rcx, [r14+10h]; lpMem
0x18000c3cf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c3d4  mov     edx, 18h; unsigned __int64
0x18000c3d9  mov     rcx, r14; void *
0x18000c3dc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c3e1  mov     [rbx+240h], r12d
0x18000c3e8  mov     [rbx+238h], rdi
0x18000c3ef  test    rdi, rdi
0x18000c3f2  jz      short loc_18000C3FE
0x18000c3f4  mov     dword ptr [rbx+240h], 1
0x18000c3fe  mov     rax, [rsi]
0x18000c401  lea     r8, [rbx+248h]
0x18000c408  lea     rdx, aRepositorydir; "RepositoryDir"
0x18000c40f  mov     rcx, rsi
0x18000c412  mov     rax, [rax+28h]
0x18000c416  call    cs:__guard_dispatch_icall_fptr
0x18000c41c  lea     rdi, [rbx+260h]
0x18000c423  mov     rax, [rsi]
0x18000c426  mov     r8, rdi
0x18000c429  lea     rdx, aRepositoryflag; "RepositoryFlags"
0x18000c430  mov     rcx, rsi
0x18000c433  mov     rax, [rax+30h]
0x18000c437  call    cs:__guard_dispatch_icall_fptr
0x18000c43d  test    al, al
0x18000c43f  jnz     short loc_18000C444
0x18000c441  mov     [rdi], r12d
0x18000c444  mov     rdx, rsi; struct IRegWrapper::Key *
0x18000c447  mov     rcx, rbx; this
0x18000c44a  call    ?BinaryDeSerializeLogicalImageList@Configuration@@QEAAXPEAVKey@IRegWrapper@@@Z; Configuration::BinaryDeSerializeLogicalImageList(IRegWrapper::Key *)
0x18000c44f  lea     rdi, [rbx+288h]
0x18000c456  mov     rax, [rsi]
0x18000c459  mov     r8, rdi
0x18000c45c  lea     rdx, aRuntimemissing; "RuntimeMissing"
0x18000c463  mov     rcx, rsi
0x18000c466  mov     rax, [rax+30h]
0x18000c46a  call    cs:__guard_dispatch_icall_fptr
0x18000c470  test    al, al
0x18000c472  jnz     short loc_18000C477
0x18000c474  mov     [rdi], r12d
0x18000c477  mov     rax, [rsi]
0x18000c47a  lea     r8, [rsp+290h+var_270]
0x18000c47f  lea     rdx, aKeepruntimever; "KeepRuntimeVersion"
0x18000c486  mov     rcx, rsi
0x18000c489  mov     rax, [rax+30h]
0x18000c48d  call    cs:__guard_dispatch_icall_fptr
0x18000c493  test    al, al
0x18000c495  jz      short loc_18000C4AB
0x18000c497  cmp     [rsp+290h+var_270], r12d
0x18000c49c  setnz   al
0x18000c49f  mov     [rbx+280h], al
0x18000c4a5  test    al, al
0x18000c4a7  jnz     short loc_18000C4E2
0x18000c4a9  jmp     short loc_18000C4B2
0x18000c4ab  mov     [rbx+280h], r12b
0x18000c4b2  cmp     dword ptr [r15], 2
0x18000c4b6  jnz     short loc_18000C4C3
0x18000c4b8  test    dword ptr [rbx+20h], 0FFFFFFF8h
0x18000c4bf  ja      short loc_18000C4E2
0x18000c4c1  jmp     short loc_18000C518
0x18000c4c3  cmp     dword ptr [r15], 3
0x18000c4c7  jz      short loc_18000C4E2
0x18000c4c9  cmp     [r15], r12d
0x18000c4cc  jnz     short loc_18000C4D7
0x18000c4ce  test    dword ptr [rbx+20h], 0FFFFFFF8h
0x18000c4d5  ja      short loc_18000C4E2
0x18000c4d7  cmp     dword ptr [r15], 5
0x18000c4db  jnz     short loc_18000C518
0x18000c4dd  cmp     [rdi], r12d
0x18000c4e0  jnz     short loc_18000C518
0x18000c4e2  mov     rax, [rsi]
0x18000c4e5  lea     r8, [rbx+268h]
0x18000c4ec  lea     rdx, aRuntimeversion; "RuntimeVersion"
0x18000c4f3  mov     rcx, rsi
0x18000c4f6  mov     rax, [rax+28h]
0x18000c4fa  call    cs:__guard_dispatch_icall_fptr
0x18000c500  test    al, al
0x18000c502  jnz     short loc_18000C518
0x18000c504  lea     rdx, aV2050727; "v2.0.50727"
0x18000c50b  lea     rcx, [rbx+268h]; this
0x18000c512  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x18000c517  nop
0x18000c518  test    [rsp+290h+var_248], 8
0x18000c51d  jz      short loc_18000C550
0x18000c51f  mov     rbx, [rsp+290h+lpMem]
0x18000c524  test    rbx, rbx
0x18000c527  jz      short loc_18000C550
0x18000c529  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18000c530  test    rax, rax
0x18000c533  jnz     short loc_18000C542
0x18000c535  call    cs:__imp_GetProcessHeap
0x18000c53b  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18000c542  mov     r8, rbx; lpMem
0x18000c545  xor     edx, edx; dwFlags
0x18000c547  mov     rcx, rax; hHeap
0x18000c54a  call    cs:__imp_HeapFree
0x18000c550  mov     rcx, [rbp+190h+var_30]
0x18000c557  xor     rcx, rsp; StackCookie
0x18000c55a  call    __security_check_cookie
0x18000c55f  lea     r11, [rsp+290h+var_20]
0x18000c567  mov     rbx, [r11+40h]
0x18000c56b  mov     rsi, [r11+48h]
0x18000c56f  mov     rsp, r11
0x18000c572  pop     r15
0x18000c574  pop     r14
0x18000c576  pop     r12
0x18000c578  pop     rdi
0x18000c579  pop     rbp
0x18000c57a  retn
0x18000c57b  mov     ecx, 800700A0h; int
0x18000c580  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
