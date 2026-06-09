# CNDFHelperClassRegistry::GetExtensions(INDFHelperClassEnum * *)

- ea: `0x180007440`
- end: `0x1800074dd`
- name: `?GetExtensions@CNDFHelperClassRegistry@@UEAAJPEAPEAUINDFHelperClassEnum@@@Z`
- size: `157`
- prototype: `__int64 __fastcall(CNDFHelperClassRegistry *__hidden this, struct INDFHelperClassEnum **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x1800071d0`
- `0x180007440`
- `0x180007a20`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180007466`
- `KERNEL32!EnterCriticalSection` at `0x180007466`
- `KERNEL32!LeaveCriticalSection` at `0x18000748c`
- `KERNEL32!LeaveCriticalSection` at `0x1800074a9`
- `KERNEL32!LeaveCriticalSection` at `0x18000748c`
- `KERNEL32!LeaveCriticalSection` at `0x1800074a9`

## pseudocode

```c
__int64 __fastcall CNDFHelperClassRegistry::GetExtensions(
        CNDFHelperClassRegistry *this,
        struct INDFHelperClassEnum **a2)
{
  __int64 result; // rax
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  int v6; // esi

  if ( !a2 )
    return 2147942487LL;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 656);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 656));
  try
  {
    if ( !*((_DWORD *)this + 158) )
    {
      v6 = CNDFHelperClassRegistry::InitializeData(this);
      if ( v6 < 0 )
      {
        LeaveCriticalSection(v5);
        return (unsigned int)v6;
      }
      *((_DWORD *)this + 158) = 1;
    }
    LeaveCriticalSection(v5);
    result = GetEnumeratorInterface((char *)this + 600, a2);
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( exception )
  {
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x180007440  push    rbx
0x180007442  push    rsi
0x180007443  push    rdi
0x180007444  push    r14
0x180007446  sub     rsp, 28h
0x18000744a  mov     r14, rdx
0x18000744d  mov     rbx, rcx
0x180007450  test    rdx, rdx
0x180007453  jnz     short loc_18000745C
0x180007455  mov     eax, 80070057h
0x18000745a  jmp     short loc_1800074D2
0x18000745c  lea     rdi, [rcx+290h]
0x180007463  mov     rcx, rdi; lpCriticalSection
0x180007466  call    cs:__imp_EnterCriticalSection
0x18000746d  nop     dword ptr [rax+rax+00h]
0x180007472  cmp     dword ptr [rbx+278h], 0
0x180007479  jnz     short loc_1800074A6
0x18000747b  mov     rcx, rbx; this
0x18000747e  call    ?InitializeData@CNDFHelperClassRegistry@@AEAAJXZ; CNDFHelperClassRegistry::InitializeData(void)
0x180007483  mov     esi, eax
0x180007485  test    eax, eax
0x180007487  jns     short loc_18000749C
0x180007489  mov     rcx, rdi; lpCriticalSection
0x18000748c  call    cs:__imp_LeaveCriticalSection
0x180007493  nop     dword ptr [rax+rax+00h]
0x180007498  mov     eax, esi
0x18000749a  jmp     short loc_1800074D2
0x18000749c  mov     dword ptr [rbx+278h], 1
0x1800074a6  mov     rcx, rdi; lpCriticalSection
0x1800074a9  call    cs:__imp_LeaveCriticalSection
0x1800074b0  nop     dword ptr [rax+rax+00h]
0x1800074b5  lea     rcx, [rbx+258h]
0x1800074bc  mov     rdx, r14
0x1800074bf  call    ?GetEnumeratorInterface@@YAJPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@@std@@PEAPEAUINDFHelperClassEnum@@@Z; GetEnumeratorInterface(std::map<std::wstring,CNDFHelperClass *> *,INDFHelperClassEnum * *)
0x1800074c4  jmp     short loc_1800074D2
0x1800074c6  mov     eax, 8007000Eh
0x1800074cb  jmp     short loc_1800074D2
0x1800074cd  mov     eax, 80004005h
0x1800074d2  add     rsp, 28h
0x1800074d6  pop     r14
0x1800074d8  pop     rdi
0x1800074d9  pop     rsi
0x1800074da  pop     rbx
0x1800074db  retn
```
