# Enumerator::`scalar deleting destructor'(uint)

- ea: `0x1800278a0`
- end: `0x180027b75`
- name: `??_GEnumerator@@UEAAPEAXI@Z`
- size: `725`
- prototype: `Enumerator *__fastcall(Enumerator *this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800278a0`
- `0x18013aee0`

## import_xrefs

- `msvcrt!?name@type_info@@QEBAPEBDXZ` at `0x1800278f8`
- `msvcrt!?name@type_info@@QEBAPEBDXZ` at `0x1800278f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027b0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027b0a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180027937`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180027937`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002796e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002796e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002797c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002797c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800278d8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800278d8`

## pseudocode

```c
Enumerator *__fastcall Enumerator::`scalar deleting destructor'(Enumerator *this, char a2)
{
  SAFEARRAY *v3; // rcx
  __int64 v5; // rsi
  const char *v6; // r9
  HANDLE ProcessHeap; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v12; // [rsp+38h] [rbp-100h]
  __int64 v13; // [rsp+40h] [rbp-F8h]
  __int64 v14; // [rsp+48h] [rbp-F0h]
  __int64 v15; // [rsp+50h] [rbp-E8h]
  int v16; // [rsp+70h] [rbp-C8h] BYREF
  Enumerator *v17; // [rsp+78h] [rbp-C0h] BYREF
  unsigned __int16 v18[64]; // [rsp+80h] [rbp-B8h] BYREF

  *(_QWORD *)this = &Enumerator::`vftable';
  v3 = (SAFEARRAY *)*((_QWORD *)this + 8);
  if ( v3 )
  {
    SafeArrayDestroy(v3);
    *((_QWORD *)this + 8) = 0;
  }
  v17 = this;
  *(_QWORD *)this = &Unknown<IEnumVARIANT>::`vftable';
  v5 = -1;
  v6 = type_info::name((type_info *)&IEnumVARIANT `RTTI Type Descriptor');
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    if ( v6 )
    {
      v9 = -1;
      do
        ++v9;
      while ( v6[v9] );
      v10 = (unsigned int)v9 + 1LL;
    }
    else
    {
      v10 = 0;
    }
    EventingWriteEvent(&g_Eventing, PLA_EVENT_DESTRUCTOR, 2, v6, v10, &v17, 8, v12, v13, v14, v15);
  }
  _InterlockedDecrement(&g_Count);
  if ( *((_DWORD *)this + 2) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( (a2 & 1) != 0 )
  {
    v17 = this;
    v16 = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000200LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000200LL) )
    {
      EventingWriteEvent(&g_Eventing, PLA_EVENT_DELETE, 3, qword_180147320, 1, &v16, 4, &v17, 8, v14, v15);
    }
    ProcessHeap = GetProcessHeap();
    if ( !HeapFree(ProcessHeap, 0, this) )
    {
      v16 = 0;
      LODWORD(v17) = GetLastError();
      if ( (_DWORD)xmmword_180169738 )
      {
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v18, 0x4000000000000800uLL);
          while ( v18[++v5] != 0 )
            ;
          EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, &v17, 4, qword_180147320, 1, &v16, 4, "PlaiFree", 9);
        }
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x1800278a0  push    rbx
0x1800278a2  push    rbp
0x1800278a3  push    rsi
0x1800278a4  push    rdi
0x1800278a5  sub     rsp, 118h
0x1800278ac  mov     rax, cs:__security_cookie
0x1800278b3  xor     rax, rsp
0x1800278b6  mov     [rsp+138h+var_38], rax
0x1800278be  lea     rax, ??_7Enumerator@@6B@; const Enumerator::`vftable'
0x1800278c5  mov     rbx, rcx
0x1800278c8  mov     [rcx], rax
0x1800278cb  xor     ebp, ebp
0x1800278cd  mov     rcx, [rcx+40h]; psa
0x1800278d1  mov     edi, edx
0x1800278d3  test    rcx, rcx
0x1800278d6  jz      short loc_1800278E2
0x1800278d8  call    cs:__imp_SafeArrayDestroy
0x1800278de  mov     [rbx+40h], rbp
0x1800278e2  lea     rax, ??_7?$Unknown@UIEnumVARIANT@@@@6B@; const Unknown<IEnumVARIANT>::`vftable'
0x1800278e9  mov     [rsp+138h+var_C0], rbx
0x1800278ee  lea     rcx, ??_R0?AUIEnumVARIANT@@@8; IEnumVARIANT `RTTI Type Descriptor'
0x1800278f5  mov     [rbx], rax
0x1800278f8  call    cs:__imp_?name@type_info@@QEBAPEBDXZ; type_info::name(void)
0x1800278fe  cmp     dword ptr cs:xmmword_180169738, ebp
0x180027904  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18002790b  mov     r9, rax
0x18002790e  jz      short loc_180027927
0x180027910  mov     rdx, 4000000000000400h
0x18002791a  test    qword ptr cs:xmmword_180169738+8, rdx
0x180027921  jnz     loc_1800279A9
0x180027927  lock dec cs:?g_Count@@3JA; long g_Count
0x18002792e  cmp     [rbx+8], ebp
0x180027931  jz      short loc_18002793D
0x180027933  lea     rcx, [rbx+10h]; lpCriticalSection
0x180027937  call    cs:__imp_DeleteCriticalSection
0x18002793d  test    dil, 1
0x180027941  jz      short loc_18002798A
0x180027943  cmp     dword ptr cs:xmmword_180169738, ebp
0x180027949  mov     [rsp+138h+var_C0], rbx
0x18002794e  mov     [rsp+138h+var_C8], ebp
0x180027952  jz      short loc_180027967
0x180027954  mov     rdx, 4000000000000200h
0x18002795e  test    qword ptr cs:xmmword_180169738+8, rdx
0x180027965  jnz     short loc_1800279DF
0x180027967  lea     rdi, qword_180147320
0x18002796e  call    cs:__imp_GetProcessHeap
0x180027974  mov     r8, rbx; lpMem
0x180027977  xor     edx, edx; dwFlags
0x180027979  mov     rcx, rax; hHeap
0x18002797c  call    cs:__imp_HeapFree
0x180027982  test    eax, eax
0x180027984  jz      loc_180027B06
0x18002798a  mov     rax, rbx
0x18002798d  mov     rcx, [rsp+138h+var_38]
0x180027995  xor     rcx, rsp; StackCookie
0x180027998  call    __security_check_cookie
0x18002799d  add     rsp, 118h
0x1800279a4  pop     rdi
0x1800279a5  pop     rsi
0x1800279a6  pop     rbp
0x1800279a7  pop     rbx
0x1800279a8  retn
0x1800279a9  mov     rax, cs:qword_180169748
0x1800279b0  and     rax, rdx
0x1800279b3  cmp     cs:qword_180169748, rax
0x1800279ba  jnz     loc_180027927
0x1800279c0  test    r9, r9
0x1800279c3  jz      loc_180027B3C
0x1800279c9  mov     rax, rsi
0x1800279cc  inc     rax
0x1800279cf  cmp     [r9+rax], bpl
0x1800279d3  jnz     short loc_1800279CC
0x1800279d5  mov     eax, eax
0x1800279d7  inc     rax
0x1800279da  jmp     loc_180027B3F
0x1800279df  mov     rax, cs:qword_180169748
0x1800279e6  and     rax, rdx
0x1800279e9  cmp     cs:qword_180169748, rax
0x1800279f0  jnz     loc_180027967
0x1800279f6  mov     [rsp+138h+var_F8], 8
0x1800279ff  lea     rax, [rsp+138h+var_C0]
0x180027a04  mov     [rsp+138h+var_100], rax
0x180027a09  lea     rdi, qword_180147320
0x180027a10  lea     rax, [rsp+138h+var_C8]
0x180027a15  mov     [rsp+138h+var_108], 4
0x180027a1e  mov     [rsp+138h+var_110], rax
0x180027a23  lea     rdx, PLA_EVENT_DELETE
0x180027a2a  mov     r9, rdi
0x180027a2d  mov     [rsp+138h+var_118], 1
0x180027a36  mov     r8d, 3
0x180027a3c  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180027a43  call    EventingWriteEvent
0x180027a48  jmp     loc_18002796E
0x180027a4d  mov     rax, cs:qword_180169748
0x180027a54  and     rax, rdx
0x180027a57  cmp     cs:qword_180169748, rax
0x180027a5e  jnz     loc_18002798A
0x180027a64  lea     rcx, [rsp+138h+var_B8]; unsigned __int16 *
0x180027a6c  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180027a71  lea     rax, [rsp+138h+var_B8]
0x180027a79  nop     dword ptr [rax+00000000h]
0x180027a80  cmp     [rax+rsi*2+2], bp
0x180027a85  lea     rsi, [rsi+1]
0x180027a89  jnz     short loc_180027A80
0x180027a8b  lea     rax, [rsp+138h+var_B8]
0x180027a93  mov     r8d, 5
0x180027a99  lea     ecx, [rsi+rsi]
0x180027a9c  add     rcx, 2
0x180027aa0  lea     r9, [rsp+138h+var_C0]
0x180027aa5  mov     [rsp+138h+var_D8], rcx
0x180027aaa  lea     rdx, PLA_EVENT_ERROR
0x180027ab1  mov     [rsp+138h+var_E0], rax
0x180027ab6  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180027abd  mov     [rsp+138h+var_E8], 9
0x180027ac6  lea     rax, aPlaifree; "PlaiFree"
0x180027acd  mov     [rsp+138h+var_F0], rax
0x180027ad2  lea     rax, [rsp+138h+var_C8]
0x180027ad7  mov     [rsp+138h+var_F8], 4
0x180027ae0  mov     [rsp+138h+var_100], rax
0x180027ae5  mov     [rsp+138h+var_108], 1
0x180027aee  mov     [rsp+138h+var_110], rdi
0x180027af3  mov     [rsp+138h+var_118], 4
0x180027afc  call    EventingWriteEvent
0x180027b01  jmp     loc_18002798A
0x180027b06  mov     [rsp+138h+var_C8], ebp
0x180027b0a  call    cs:__imp_GetLastError
0x180027b10  cmp     dword ptr cs:xmmword_180169738, ebp
0x180027b16  mov     dword ptr [rsp+138h+var_C0], eax
0x180027b1a  jz      loc_18002798A
0x180027b20  mov     rdx, 4000000000000800h; unsigned __int64
0x180027b2a  test    qword ptr cs:xmmword_180169738+8, rdx
0x180027b31  jz      loc_18002798A
0x180027b37  jmp     loc_180027A4D
0x180027b3c  mov     rax, rbp
0x180027b3f  lea     rcx, [rsp+138h+var_C0]
0x180027b44  mov     [rsp+138h+var_108], 8
0x180027b4d  mov     [rsp+138h+var_110], rcx
0x180027b52  lea     rdx, PLA_EVENT_DESTRUCTOR
0x180027b59  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180027b60  mov     [rsp+138h+var_118], rax
0x180027b65  mov     r8d, 2
0x180027b6b  call    EventingWriteEvent
0x180027b70  jmp     loc_180027927
```
