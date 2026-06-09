# CNDFLanguageUtil::~CNDFLanguageUtil(void)

- ea: `0x1800040d4`
- end: `0x18000410e`
- name: `??1CNDFLanguageUtil@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(CNDFLanguageUtil *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004940`
- `0x18002cce1`

## callees

- `0x1800040d4`

## import_xrefs

- `KERNEL32!SetThreadPreferredUILanguages` at `0x1800040f9`
- `KERNEL32!SetThreadPreferredUILanguages` at `0x1800040f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004107`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CNDFLanguageUtil::~CNDFLanguageUtil(CNDFLanguageUtil *this)
{
  LPVOID *v1; // rbx
  const WCHAR *v2; // rdx
  ULONG pulNumLanguages; // [rsp+30h] [rbp+8h] BYREF

  v1 = (LPVOID *)((char *)this + 16);
  if ( *((_DWORD *)this + 7) )
  {
    v2 = (const WCHAR *)*v1;
    pulNumLanguages = 0;
    SetThreadPreferredUILanguages(8u, v2, &pulNumLanguages);
  }
  CoTaskMemFree(*v1);
}

```

## disassembly

```asm
0x1800040d4  push    rbx
0x1800040d6  sub     rsp, 20h
0x1800040da  cmp     dword ptr [rcx+1Ch], 0
0x1800040de  lea     rbx, [rcx+10h]
0x1800040e2  jz      short loc_1800040FF
0x1800040e4  mov     rdx, [rbx]; pwszLanguagesBuffer
0x1800040e7  lea     r8, [rsp+28h+pulNumLanguages]; pulNumLanguages
0x1800040ec  mov     ecx, 8; dwFlags
0x1800040f1  mov     [rsp+28h+pulNumLanguages], 0
0x1800040f9  call    cs:__imp_SetThreadPreferredUILanguages
0x1800040ff  mov     rcx, [rbx]
0x180004102  add     rsp, 20h
0x180004106  pop     rbx
0x180004107  jmp     cs:__imp_CoTaskMemFree
```
