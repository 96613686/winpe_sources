# CNDFHelperClassRegistry::GetHelperClasses(INDFHelperClassEnum * *)

- ea: `0x180007750`
- end: `0x1800077ed`
- name: `?GetHelperClasses@CNDFHelperClassRegistry@@UEAAJPEAPEAUINDFHelperClassEnum@@@Z`
- size: `157`
- prototype: `__int64 __fastcall(CNDFHelperClassRegistry *__hidden this, struct INDFHelperClassEnum **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1800071d0`
- `0x180007750`
- `0x180007a20`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180007776`
- `KERNEL32!EnterCriticalSection` at `0x180007776`
- `KERNEL32!LeaveCriticalSection` at `0x18000779c`
- `KERNEL32!LeaveCriticalSection` at `0x1800077b9`
- `KERNEL32!LeaveCriticalSection` at `0x18000779c`
- `KERNEL32!LeaveCriticalSection` at `0x1800077b9`

## pseudocode

```c
__int64 __fastcall CNDFHelperClassRegistry::GetHelperClasses(
        CNDFHelperClassRegistry *this,
        struct INDFHelperClassEnum **a2)
{
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  int v6; // esi

  if ( !a2 )
    return 2147942487LL;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 656);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 656));
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
  return GetEnumeratorInterface((char *)this + 584, a2);
}

```

## disassembly

```asm
0x180007750  push    rbx
0x180007752  push    rsi
0x180007753  push    rdi
0x180007754  push    r14
0x180007756  sub     rsp, 28h
0x18000775a  mov     r14, rdx
0x18000775d  mov     rbx, rcx
0x180007760  test    rdx, rdx
0x180007763  jnz     short loc_18000776C
0x180007765  mov     eax, 80070057h
0x18000776a  jmp     short loc_1800077E2
0x18000776c  lea     rdi, [rcx+290h]
0x180007773  mov     rcx, rdi; lpCriticalSection
0x180007776  call    cs:__imp_EnterCriticalSection
0x18000777d  nop     dword ptr [rax+rax+00h]
0x180007782  cmp     dword ptr [rbx+278h], 0
0x180007789  jnz     short loc_1800077B6
0x18000778b  mov     rcx, rbx; this
0x18000778e  call    ?InitializeData@CNDFHelperClassRegistry@@AEAAJXZ; CNDFHelperClassRegistry::InitializeData(void)
0x180007793  mov     esi, eax
0x180007795  test    eax, eax
0x180007797  jns     short loc_1800077AC
0x180007799  mov     rcx, rdi; lpCriticalSection
0x18000779c  call    cs:__imp_LeaveCriticalSection
0x1800077a3  nop     dword ptr [rax+rax+00h]
0x1800077a8  mov     eax, esi
0x1800077aa  jmp     short loc_1800077E2
0x1800077ac  mov     dword ptr [rbx+278h], 1
0x1800077b6  mov     rcx, rdi; lpCriticalSection
0x1800077b9  call    cs:__imp_LeaveCriticalSection
0x1800077c0  nop     dword ptr [rax+rax+00h]
0x1800077c5  lea     rcx, [rbx+248h]
0x1800077cc  mov     rdx, r14
0x1800077cf  call    ?GetEnumeratorInterface@@YAJPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@@std@@PEAPEAUINDFHelperClassEnum@@@Z; GetEnumeratorInterface(std::map<std::wstring,CNDFHelperClass *> *,INDFHelperClassEnum * *)
0x1800077d4  jmp     short loc_1800077E2
0x1800077d6  mov     eax, 8007000Eh
0x1800077db  jmp     short loc_1800077E2
0x1800077dd  mov     eax, 80004005h
0x1800077e2  add     rsp, 28h
0x1800077e6  pop     r14
0x1800077e8  pop     rdi
0x1800077e9  pop     rsi
0x1800077ea  pop     rbx
0x1800077eb  retn
```
