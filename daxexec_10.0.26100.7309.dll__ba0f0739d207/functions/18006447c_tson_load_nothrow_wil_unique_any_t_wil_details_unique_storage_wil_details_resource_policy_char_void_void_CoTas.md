# tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::input_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)

- ea: `0x18006447c`
- end: `0x18006468a`
- name: `??$load_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z`
- size: `526`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180061a30`

## callees

- `0x180061634`
- `0x18006447c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006453f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064621`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006453f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064621`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006452b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006459f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006460d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006452b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006459f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006460d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800645b3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800645b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180064513`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800645f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006465d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180064513`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800645f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006465d`

## pseudocode

```c
void __fastcall tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        tson::input_archive *this,
        void **a2)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  char *v6; // rax
  __int64 v7; // rax
  unsigned __int16 v8; // cx
  unsigned __int16 *v9; // rdx
  unsigned __int64 v10; // rdi
  void *v11; // rcx
  void *v12; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int64 v14; // rax
  __int64 v15; // rbp
  HANDLE v16; // rax
  _QWORD *v17; // r15
  char v18; // al
  unsigned __int64 v19; // rdi
  _QWORD *v20; // rcx
  void *v21; // rcx
  void *v22; // rdi
  HANDLE v23; // rax
  void *v24; // rcx
  void *v25; // [rsp+50h] [rbp+8h] BYREF

  v4 = 0;
  if ( !*((_BYTE *)this + 25) )
  {
    v5 = *((_QWORD *)this + 17);
    if ( v5 )
    {
      v6 = (char *)this + 4 * v5 + 32;
    }
    else
    {
      *((_BYTE *)this + 32) = 1;
      v6 = (char *)this + 36;
    }
    if ( *(_DWORD *)v6 != 1 && *((int *)this + 2) >= 0 )
      *((_DWORD *)this + 2) = -2147023267;
    v7 = *(_QWORD *)this;
    v8 = 0;
    v9 = *(unsigned __int16 **)(*(_QWORD *)this + 8LL);
    if ( (unsigned __int64)(v9 + 1) > *(_QWORD *)(*(_QWORD *)this + 16LL) )
    {
      *(_BYTE *)(v7 + 24) = 1;
    }
    else
    {
      v8 = *v9;
      *(_QWORD *)(v7 + 8) = v9 + 1;
    }
    v4 = v8;
  }
  if ( *a2 )
  {
    v10 = 0;
    if ( a2[2] )
    {
      do
      {
        v11 = (void *)*((_QWORD *)*a2 + v10);
        if ( v11 )
          CoTaskMemFree(v11);
        ++v10;
      }
      while ( v10 < (unsigned __int64)a2[2] );
    }
    v12 = *a2;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v12);
    *a2 = 0;
  }
  a2[1] = 0;
  a2[2] = 0;
  while ( v4 )
  {
    v25 = 0;
    --v4;
    tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(
      this,
      &v25);
    v14 = (unsigned __int64)a2[1];
    if ( (unsigned __int64)a2[2] < v14 )
      goto LABEL_36;
    if ( v14 )
    {
      v15 = 2 * v14;
      if ( 2 * v14 <= v14 )
        goto LABEL_33;
    }
    else
    {
      v15 = 10;
    }
    v16 = GetProcessHeap();
    v17 = HeapAlloc(v16, 0, 8 * v15);
    if ( !v17 )
    {
      v18 = 0;
      goto LABEL_34;
    }
    if ( *a2 )
    {
      v19 = 0;
      if ( a2[2] )
      {
        do
        {
          v20 = *a2;
          v17[v19] = *((_QWORD *)*a2 + v19);
          v20[v19] = 0;
          v21 = (void *)*((_QWORD *)*a2 + v19);
          if ( v21 )
            CoTaskMemFree(v21);
          ++v19;
        }
        while ( v19 < (unsigned __int64)a2[2] );
      }
      v22 = *a2;
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v22);
    }
    *a2 = v17;
    a2[1] = (void *)v15;
LABEL_33:
    v18 = 1;
LABEL_34:
    if ( v18 )
    {
LABEL_36:
      *((_QWORD *)*a2 + (_QWORD)a2[2]) = v25;
      v24 = 0;
      a2[2] = (char *)a2[2] + 1;
      goto LABEL_37;
    }
    v24 = v25;
LABEL_37:
    if ( v24 )
      CoTaskMemFree(v24);
  }
}

```

## disassembly

```asm
0x18006447c  mov     [rsp+arg_8], rbx
0x180064481  mov     [rsp+arg_10], rbp
0x180064486  push    rsi
0x180064487  push    rdi
0x180064488  push    r12
0x18006448a  push    r14
0x18006448c  push    r15
0x18006448e  sub     rsp, 20h
0x180064492  xor     r12d, r12d
0x180064495  mov     rsi, rdx
0x180064498  mov     r14, rcx
0x18006449b  mov     ebx, r12d
0x18006449e  cmp     [rcx+19h], r12b
0x1800644a2  jnz     short loc_1800644F9
0x1800644a4  mov     rax, [rcx+88h]
0x1800644ab  test    rax, rax
0x1800644ae  jz      short loc_1800644BA
0x1800644b0  add     rax, 8
0x1800644b4  lea     rax, [rcx+rax*4]
0x1800644b8  jmp     short loc_1800644C2
0x1800644ba  mov     byte ptr [rcx+20h], 1
0x1800644be  lea     rax, [rcx+24h]
0x1800644c2  cmp     dword ptr [rax], 1
0x1800644c5  jz      short loc_1800644D4
0x1800644c7  cmp     [rcx+8], r12d
0x1800644cb  jl      short loc_1800644D4
0x1800644cd  mov     dword ptr [rcx+8], 8007065Dh
0x1800644d4  mov     rax, [r14]
0x1800644d7  movzx   ecx, r12w
0x1800644db  mov     rdx, [rax+8]
0x1800644df  lea     r8, [rdx+2]
0x1800644e3  cmp     r8, [rax+10h]
0x1800644e7  ja      short loc_1800644F2
0x1800644e9  movzx   ecx, word ptr [rdx]
0x1800644ec  mov     [rax+8], r8
0x1800644f0  jmp     short loc_1800644F6
0x1800644f2  mov     byte ptr [rax+18h], 1
0x1800644f6  movzx   ebx, cx
0x1800644f9  cmp     [rsi], r12
0x1800644fc  jz      short loc_18006454E
0x1800644fe  mov     rdi, r12
0x180064501  cmp     [rsi+10h], r12
0x180064505  jbe     short loc_180064528
0x180064507  mov     rax, [rsi]
0x18006450a  mov     rcx, [rax+rdi*8]; pv
0x18006450e  test    rcx, rcx
0x180064511  jz      short loc_18006451F
0x180064513  call    cs:__imp_CoTaskMemFree
0x18006451a  nop     dword ptr [rax+rax+00h]
0x18006451f  inc     rdi
0x180064522  cmp     rdi, [rsi+10h]
0x180064526  jb      short loc_180064507
0x180064528  mov     rdi, [rsi]
0x18006452b  call    cs:__imp_GetProcessHeap
0x180064532  nop     dword ptr [rax+rax+00h]
0x180064537  mov     r8, rdi; lpMem
0x18006453a  xor     edx, edx; dwFlags
0x18006453c  mov     rcx, rax; hHeap
0x18006453f  call    cs:__imp_HeapFree
0x180064546  nop     dword ptr [rax+rax+00h]
0x18006454b  mov     [rsi], r12
0x18006454e  mov     [rsi+8], r12
0x180064552  mov     [rsi+10h], r12
0x180064556  jmp     loc_180064669
0x18006455b  lea     rdx, [rsp+48h+arg_0]
0x180064560  mov     [rsp+48h+arg_0], r12
0x180064565  mov     rcx, r14; this
0x180064568  dec     rbx
0x18006456b  call    ??$?RAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@QEAAAEAV01@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)
0x180064570  mov     rax, [rsi+8]
0x180064574  cmp     [rsi+10h], rax
0x180064578  jb      loc_180064641
0x18006457e  test    rax, rax
0x180064581  jz      short loc_180064592
0x180064583  lea     rbp, [rax+rax]
0x180064587  cmp     rbp, rax
0x18006458a  jbe     loc_180064634
0x180064590  jmp     short loc_180064597
0x180064592  mov     ebp, 0Ah
0x180064597  lea     rdi, ds:0[rbp*8]
0x18006459f  call    cs:__imp_GetProcessHeap
0x1800645a6  nop     dword ptr [rax+rax+00h]
0x1800645ab  mov     r8, rdi; dwBytes
0x1800645ae  xor     edx, edx; dwFlags
0x1800645b0  mov     rcx, rax; hHeap
0x1800645b3  call    cs:__imp_HeapAlloc
0x1800645ba  nop     dword ptr [rax+rax+00h]
0x1800645bf  mov     r15, rax
0x1800645c2  test    rax, rax
0x1800645c5  jnz     short loc_1800645CC
0x1800645c7  mov     al, r12b
0x1800645ca  jmp     short loc_180064636
0x1800645cc  cmp     [rsi], r12
0x1800645cf  jz      short loc_18006462D
0x1800645d1  mov     rdi, r12
0x1800645d4  cmp     [rsi+10h], r12
0x1800645d8  jbe     short loc_18006460A
0x1800645da  mov     rcx, [rsi]
0x1800645dd  mov     rax, [rcx+rdi*8]
0x1800645e1  mov     [r15+rdi*8], rax
0x1800645e5  mov     [rcx+rdi*8], r12
0x1800645e9  mov     rax, [rsi]
0x1800645ec  mov     rcx, [rax+rdi*8]; pv
0x1800645f0  test    rcx, rcx
0x1800645f3  jz      short loc_180064601
0x1800645f5  call    cs:__imp_CoTaskMemFree
0x1800645fc  nop     dword ptr [rax+rax+00h]
0x180064601  inc     rdi
0x180064604  cmp     rdi, [rsi+10h]
0x180064608  jb      short loc_1800645DA
0x18006460a  mov     rdi, [rsi]
0x18006460d  call    cs:__imp_GetProcessHeap
0x180064614  nop     dword ptr [rax+rax+00h]
0x180064619  mov     r8, rdi; lpMem
0x18006461c  xor     edx, edx; dwFlags
0x18006461e  mov     rcx, rax; hHeap
0x180064621  call    cs:__imp_HeapFree
0x180064628  nop     dword ptr [rax+rax+00h]
0x18006462d  mov     [rsi], r15
0x180064630  mov     [rsi+8], rbp
0x180064634  mov     al, 1
0x180064636  test    al, al
0x180064638  jnz     short loc_180064641
0x18006463a  mov     rcx, [rsp+48h+arg_0]
0x18006463f  jmp     short loc_180064658
0x180064641  mov     rdx, [rsi+10h]
0x180064645  mov     rcx, [rsi]
0x180064648  mov     rax, [rsp+48h+arg_0]
0x18006464d  mov     [rcx+rdx*8], rax
0x180064651  mov     rcx, r12; pv
0x180064654  inc     qword ptr [rsi+10h]
0x180064658  test    rcx, rcx
0x18006465b  jz      short loc_180064669
0x18006465d  call    cs:__imp_CoTaskMemFree
0x180064664  nop     dword ptr [rax+rax+00h]
0x180064669  test    rbx, rbx
0x18006466c  jnz     loc_18006455B
0x180064672  mov     rbx, [rsp+48h+arg_8]
0x180064677  mov     rbp, [rsp+48h+arg_10]
0x18006467c  add     rsp, 20h
0x180064680  pop     r15
0x180064682  pop     r14
0x180064684  pop     r12
0x180064686  pop     rdi
0x180064687  pop     rsi
0x180064688  retn
```
