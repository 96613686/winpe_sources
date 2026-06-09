# CRegistry::~CRegistry(void)

- ea: `0x180007158`
- end: `0x1800071b9`
- name: `??1CRegistry@@UEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CRegistry *__hidden this)`
- caller_count: `10`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000c5a0`
- `0x18000ec40`
- `0x180016840`
- `0x18001c960`
- `0x18001cab0`
- `0x18001d080`
- `0x18001d2f0`
- `0x180025252`
- `0x1800266f7`
- `0x180026893`

## callees

- `0x180005720`
- `0x180007158`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007180`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007180`

## pseudocode

```c
void __fastcall CRegistry::~CRegistry(CRegistry *this)
{
  HKEY v2; // rcx

  *(_QWORD *)this = &CRegistry::`vftable';
  v2 = (HKEY)*((_QWORD *)this + 22);
  if ( v2 && *((_DWORD *)this + 42) )
    RegCloseKey(v2);
  *(_QWORD *)this = &PConfigNode::`vftable';
  *((_QWORD *)this + 1) = &TLMString<64,64,32767>::`vftable';
  CLMString::DeleteBuf((CRegistry *)((char *)this + 8), (const wchar_t *)this + 16);
  *((_QWORD *)this + 1) = &CLMString::`vftable';
}

```

## disassembly

```asm
0x180007158  push    rbx
0x18000715a  sub     rsp, 20h
0x18000715e  mov     rbx, rcx
0x180007161  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x180007168  mov     [rcx], rax
0x18000716b  mov     rcx, [rcx+0B0h]; hKey
0x180007172  test    rcx, rcx
0x180007175  jz      short loc_180007186
0x180007177  cmp     dword ptr [rbx+0A8h], 0
0x18000717e  jz      short loc_180007186
0x180007180  call    cs:__imp_RegCloseKey
0x180007186  lea     rax, ??_7PConfigNode@@6B@; const PConfigNode::`vftable'
0x18000718d  mov     [rbx], rax
0x180007190  lea     rax, ??_7?$TLMString@$0EA@$0EA@$0HPPP@@@6B@; const TLMString<64,64,32767>::`vftable'
0x180007197  mov     [rbx+8], rax
0x18000719b  lea     rdx, [rbx+20h]; wchar_t *
0x18000719f  lea     rcx, [rbx+8]; this
0x1800071a3  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x1800071a8  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x1800071af  mov     [rbx+8], rax
0x1800071b3  add     rsp, 20h
0x1800071b7  pop     rbx
0x1800071b8  retn
```
