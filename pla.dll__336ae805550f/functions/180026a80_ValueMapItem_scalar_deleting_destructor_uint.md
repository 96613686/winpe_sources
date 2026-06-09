# ValueMapItem::`scalar deleting destructor'(uint)

- ea: `0x180026a80`
- end: `0x180026ecd`
- name: `??_GValueMapItem@@UEAAPEAXI@Z`
- size: `1101`
- prototype: `void *__fastcall(ValueMapItem *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180026a80`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `msvcrt!?name@type_info@@QEBAPEBDXZ` at `0x180026b29`
- `msvcrt!?name@type_info@@QEBAPEBDXZ` at `0x180026b29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026e4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026e4a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026b65`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026b65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026b8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026b8f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026b9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026b9d`
- `OLEAUT32!__imp_SysFreeString` at `0x180026beb`
- `OLEAUT32!__imp_SysFreeString` at `0x180026c17`
- `OLEAUT32!__imp_SysFreeString` at `0x180026beb`
- `OLEAUT32!__imp_SysFreeString` at `0x180026c17`
- `OLEAUT32!__imp_VariantClear` at `0x180026abf`
- `OLEAUT32!__imp_VariantClear` at `0x180026abf`

## pseudocode

```c
ValueMapItem *__fastcall ValueMapItem::`scalar deleting destructor'(ValueMapItem *this, char a2)
{
  VARIANTARG *v2; // rdi
  OLECHAR *v5; // rdi
  OLECHAR *v6; // rdi
  __int64 v7; // rcx
  const char *v8; // rax
  __int64 v9; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v12; // rcx
  ValueMapItem *v14; // [rsp+78h] [rbp-D0h] BYREF
  unsigned __int16 v15[64]; // [rsp+80h] [rbp-C8h] BYREF

  v2 = (VARIANTARG *)((char *)this + 72);
  *(_QWORD *)this = &ValueMapItem::`vftable';
  if ( this != (ValueMapItem *)-72LL )
  {
    VariantClear(v2);
    v2->llVal = 0;
  }
  v5 = (OLECHAR *)*((_QWORD *)this + 13);
  if ( v5 )
  {
    v14 = (ValueMapItem *)*((_QWORD *)this + 13);
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000200LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000200LL) )
    {
      EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_FREE_STRING, 3, (__int64)byte_180147320);
    }
    SysFreeString(v5);
  }
  v6 = (OLECHAR *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 13) = 0;
  if ( v6 )
  {
    v14 = (ValueMapItem *)v6;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000200LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000200LL) )
    {
      EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_FREE_STRING, 3, (__int64)byte_180147320);
    }
    SysFreeString(v6);
  }
  v7 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 14) = 0;
  *(_QWORD *)this = &Dispatch<IValueMapItem>::`vftable';
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 8) = 0;
  }
  v14 = this;
  *(_QWORD *)this = &Unknown<IValueMapItem>::`vftable';
  v8 = type_info::name((type_info *)&IValueMapItem `RTTI Type Descriptor');
  v9 = -1;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    if ( v8 )
    {
      v12 = -1;
      do
        ++v12;
      while ( v8[v12] );
    }
    EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_DESTRUCTOR, 2, (__int64)v8);
  }
  _InterlockedDecrement(&g_Count);
  if ( *((_DWORD *)this + 2) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( (a2 & 1) != 0 )
  {
    v14 = this;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000200LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000200LL) )
    {
      EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_DELETE, 3, (__int64)byte_180147320);
    }
    ProcessHeap = GetProcessHeap();
    if ( !HeapFree(ProcessHeap, 0, this) )
    {
      LODWORD(v14) = GetLastError();
      if ( (_DWORD)xmmword_180169738 )
      {
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v15, 0x4000000000000800uLL);
          while ( v15[++v9] != 0 )
            ;
          EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_ERROR, 5, (__int64)&v14);
        }
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x180026a80  push    rbx
0x180026a82  push    rbp
0x180026a83  push    rsi
0x180026a84  push    rdi
0x180026a85  push    r14
0x180026a87  push    r15
0x180026a89  sub     rsp, 118h
0x180026a90  mov     rax, cs:__security_cookie
0x180026a97  xor     rax, rsp
0x180026a9a  mov     [rsp+148h+var_48], rax
0x180026aa2  lea     rdi, [rcx+48h]
0x180026aa6  xor     ebp, ebp
0x180026aa8  lea     rax, ??_7ValueMapItem@@6B@; const ValueMapItem::`vftable'
0x180026aaf  mov     esi, edx
0x180026ab1  mov     [rcx], rax
0x180026ab4  mov     rbx, rcx
0x180026ab7  test    rdi, rdi
0x180026aba  jz      short loc_180026AC9
0x180026abc  mov     rcx, rdi; pvarg
0x180026abf  call    cs:__imp_VariantClear
0x180026ac5  mov     [rdi+8], rbp
0x180026ac9  mov     rdi, [rbx+68h]
0x180026acd  lea     r15, byte_180147320
0x180026ad4  mov     r14, 4000000000000200h
0x180026ade  test    rdi, rdi
0x180026ae1  jnz     loc_180026BCE
0x180026ae7  mov     rdi, [rbx+70h]
0x180026aeb  mov     [rbx+68h], rbp
0x180026aef  test    rdi, rdi
0x180026af2  jnz     loc_180026BF6
0x180026af8  mov     rcx, [rbx+40h]
0x180026afc  lea     rax, ??_7?$Dispatch@UIValueMapItem@@@@6B@; const Dispatch<IValueMapItem>::`vftable'
0x180026b03  mov     [rbx+70h], rbp
0x180026b07  mov     [rbx], rax
0x180026b0a  test    rcx, rcx
0x180026b0d  jnz     loc_180026E7C
0x180026b13  lea     rax, ??_7?$Unknown@UIValueMapItem@@@@6B@; const Unknown<IValueMapItem>::`vftable'
0x180026b1a  mov     [rsp+148h+var_D0], rbx
0x180026b1f  lea     rcx, ??_R0?AUIValueMapItem@@@8; IValueMapItem `RTTI Type Descriptor'
0x180026b26  mov     [rbx], rax
0x180026b29  call    cs:__imp_?name@type_info@@QEBAPEBDXZ; type_info::name(void)
0x180026b2f  cmp     dword ptr cs:xmmword_180169738, ebp
0x180026b35  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180026b3c  jz      short loc_180026B55
0x180026b3e  mov     r8, 4000000000000400h
0x180026b48  test    qword ptr cs:xmmword_180169738+8, r8
0x180026b4f  jnz     loc_180026C22
0x180026b55  lock dec cs:?g_Count@@3JA; long g_Count
0x180026b5c  cmp     [rbx+8], ebp
0x180026b5f  jz      short loc_180026B6B
0x180026b61  lea     rcx, [rbx+10h]; lpCriticalSection
0x180026b65  call    cs:__imp_DeleteCriticalSection
0x180026b6b  test    sil, 1
0x180026b6f  jz      short loc_180026BAB
0x180026b71  cmp     dword ptr cs:xmmword_180169738, ebp
0x180026b77  mov     [rsp+148h+var_D0], rbx
0x180026b7c  mov     [rsp+148h+var_D8], ebp
0x180026b80  jz      short loc_180026B8F
0x180026b82  test    qword ptr cs:xmmword_180169738+8, r14
0x180026b89  jnz     loc_180026D26
0x180026b8f  call    cs:__imp_GetProcessHeap
0x180026b95  mov     r8, rbx; lpMem
0x180026b98  xor     edx, edx; dwFlags
0x180026b9a  mov     rcx, rax; hHeap
0x180026b9d  call    cs:__imp_HeapFree
0x180026ba3  test    eax, eax
0x180026ba5  jz      loc_180026E46
0x180026bab  mov     rax, rbx
0x180026bae  mov     rcx, [rsp+148h+var_48]
0x180026bb6  xor     rcx, rsp; StackCookie
0x180026bb9  call    __security_check_cookie
0x180026bbe  add     rsp, 118h
0x180026bc5  pop     r15
0x180026bc7  pop     r14
0x180026bc9  pop     rdi
0x180026bca  pop     rsi
0x180026bcb  pop     rbp
0x180026bcc  pop     rbx
0x180026bcd  retn
0x180026bce  cmp     dword ptr cs:xmmword_180169738, ebp
0x180026bd4  mov     [rsp+148h+var_D0], rdi
0x180026bd9  mov     [rsp+148h+var_D8], ebp
0x180026bdd  jz      short loc_180026BE8
0x180026bdf  test    qword ptr cs:xmmword_180169738+8, r14
0x180026be6  jnz     short loc_180026C58
0x180026be8  mov     rcx, rdi; bstrString
0x180026beb  call    cs:__imp_SysFreeString
0x180026bf1  jmp     loc_180026AE7
0x180026bf6  cmp     dword ptr cs:xmmword_180169738, ebp
0x180026bfc  mov     [rsp+148h+var_D0], rdi
0x180026c01  mov     [rsp+148h+var_D8], ebp
0x180026c05  jz      short loc_180026C14
0x180026c07  test    qword ptr cs:xmmword_180169738+8, r14
0x180026c0e  jnz     loc_180026CBF
0x180026c14  mov     rcx, rdi; bstrString
0x180026c17  call    cs:__imp_SysFreeString
0x180026c1d  jmp     loc_180026AF8
0x180026c22  mov     rcx, cs:qword_180169748
0x180026c29  and     rcx, r8
0x180026c2c  cmp     cs:qword_180169748, rcx
0x180026c33  jnz     loc_180026B55
0x180026c39  test    rax, rax
0x180026c3c  jz      loc_180026E91
0x180026c42  mov     rcx, rdi
0x180026c45  inc     rcx
0x180026c48  cmp     [rax+rcx], bpl
0x180026c4c  jnz     short loc_180026C45
0x180026c4e  mov     ecx, ecx
0x180026c50  inc     rcx
0x180026c53  jmp     loc_180026E94
0x180026c58  mov     rax, cs:qword_180169748
0x180026c5f  and     rax, r14
0x180026c62  cmp     cs:qword_180169748, rax
0x180026c69  jnz     loc_180026BE8
0x180026c6f  mov     [rsp+148h+var_108], 8
0x180026c78  lea     rax, [rsp+148h+var_D0]
0x180026c7d  mov     [rsp+148h+var_110], rax
0x180026c82  lea     rdx, PLA_EVENT_FREE_STRING
0x180026c89  lea     rax, [rsp+148h+var_D8]
0x180026c8e  mov     [rsp+148h+var_118], 4
0x180026c97  mov     [rsp+148h+var_120], rax
0x180026c9c  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180026ca3  mov     r9, r15
0x180026ca6  mov     [rsp+148h+var_128], 1
0x180026caf  mov     r8d, 3
0x180026cb5  call    EventingWriteEvent
0x180026cba  jmp     loc_180026BE8
0x180026cbf  mov     rax, cs:qword_180169748
0x180026cc6  and     rax, r14
0x180026cc9  cmp     cs:qword_180169748, rax
0x180026cd0  jnz     loc_180026C14
0x180026cd6  mov     [rsp+148h+var_108], 8
0x180026cdf  lea     rax, [rsp+148h+var_D0]
0x180026ce4  mov     [rsp+148h+var_110], rax
0x180026ce9  lea     rdx, PLA_EVENT_FREE_STRING
0x180026cf0  lea     rax, [rsp+148h+var_D8]
0x180026cf5  mov     [rsp+148h+var_118], 4
0x180026cfe  mov     [rsp+148h+var_120], rax
0x180026d03  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180026d0a  mov     r9, r15
0x180026d0d  mov     [rsp+148h+var_128], 1
0x180026d16  mov     r8d, 3
0x180026d1c  call    EventingWriteEvent
0x180026d21  jmp     loc_180026C14
0x180026d26  mov     rax, cs:qword_180169748
0x180026d2d  and     rax, r14
0x180026d30  cmp     cs:qword_180169748, rax
0x180026d37  jnz     loc_180026B8F
0x180026d3d  mov     [rsp+148h+var_108], 8
0x180026d46  lea     rax, [rsp+148h+var_D0]
0x180026d4b  mov     [rsp+148h+var_110], rax
0x180026d50  lea     rdx, PLA_EVENT_DELETE
0x180026d57  lea     rax, [rsp+148h+var_D8]
0x180026d5c  mov     [rsp+148h+var_118], 4
0x180026d65  mov     [rsp+148h+var_120], rax
0x180026d6a  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180026d71  mov     r9, r15
0x180026d74  mov     [rsp+148h+var_128], 1
0x180026d7d  mov     r8d, 3
0x180026d83  call    EventingWriteEvent
0x180026d88  jmp     loc_180026B8F
0x180026d8d  mov     rax, cs:qword_180169748
0x180026d94  and     rax, rdx
0x180026d97  cmp     cs:qword_180169748, rax
0x180026d9e  jnz     loc_180026BAB
0x180026da4  lea     rcx, [rsp+148h+var_C8]; unsigned __int16 *
0x180026dac  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180026db1  lea     rax, [rsp+148h+var_C8]
0x180026db9  nop     dword ptr [rax+00000000h]
0x180026dc0  cmp     [rax+rdi*2+2], bp
0x180026dc5  lea     rdi, [rdi+1]
0x180026dc9  jnz     short loc_180026DC0
0x180026dcb  lea     rax, [rsp+148h+var_C8]
0x180026dd3  mov     r8d, 5
0x180026dd9  lea     ecx, [rdi+rdi]
0x180026ddc  add     rcx, 2
0x180026de0  lea     r9, [rsp+148h+var_D0]
0x180026de5  mov     [rsp+148h+var_E8], rcx
0x180026dea  lea     rdx, PLA_EVENT_ERROR
0x180026df1  mov     [rsp+148h+var_F0], rax
0x180026df6  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180026dfd  mov     [rsp+148h+var_F8], 9
0x180026e06  lea     rax, aPlaifree; "PlaiFree"
0x180026e0d  mov     [rsp+148h+var_100], rax
0x180026e12  lea     rax, [rsp+148h+var_D8]
0x180026e17  mov     [rsp+148h+var_108], 4
0x180026e20  mov     [rsp+148h+var_110], rax
0x180026e25  mov     [rsp+148h+var_118], 1
0x180026e2e  mov     [rsp+148h+var_120], r15
0x180026e33  mov     [rsp+148h+var_128], 4
0x180026e3c  call    EventingWriteEvent
0x180026e41  jmp     loc_180026BAB
0x180026e46  mov     [rsp+148h+var_D8], ebp
0x180026e4a  call    cs:__imp_GetLastError
0x180026e50  cmp     dword ptr cs:xmmword_180169738, ebp
0x180026e56  mov     dword ptr [rsp+148h+var_D0], eax
0x180026e5a  jz      loc_180026BAB
0x180026e60  mov     rdx, 4000000000000800h; unsigned __int64
0x180026e6a  test    qword ptr cs:xmmword_180169738+8, rdx
0x180026e71  jz      loc_180026BAB
0x180026e77  jmp     loc_180026D8D
0x180026e7c  mov     rax, [rcx]
0x180026e7f  mov     rax, [rax+10h]
0x180026e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e88  mov     [rbx+40h], rbp
0x180026e8c  jmp     loc_180026B13
0x180026e91  mov     rcx, rbp
0x180026e94  lea     rdx, [rsp+148h+var_D0]
0x180026e99  mov     [rsp+148h+var_118], 8
0x180026ea2  mov     [rsp+148h+var_120], rdx
0x180026ea7  mov     r9, rax
0x180026eaa  mov     [rsp+148h+var_128], rcx
0x180026eaf  lea     rdx, PLA_EVENT_DESTRUCTOR
0x180026eb6  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180026ebd  mov     r8d, 2
0x180026ec3  call    EventingWriteEvent
0x180026ec8  jmp     loc_180026B55
```
