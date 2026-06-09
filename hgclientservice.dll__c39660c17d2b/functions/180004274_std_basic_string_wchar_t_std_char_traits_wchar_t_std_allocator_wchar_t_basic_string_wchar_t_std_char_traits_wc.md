# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)

- ea: `0x180004274`
- end: `0x1800042d8`
- name: `??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `51`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180007920`
- `0x180008500`
- `0x180009300`
- `0x1800096d0`
- `0x18000c1d8`
- `0x18000c538`
- `0x18000c574`
- `0x18000c890`
- `0x18000d4d8`
- `0x18000e100`
- `0x18000e8dc`
- `0x18000e944`
- `0x18000ebf0`
- `0x18000ec58`
- `0x18000ecc8`
- `0x18000edb0`
- `0x18000ee44`
- `0x18000efe0`
- `0x18000f1ac`
- `0x18000f814`
- `0x18000fe14`
- `0x180010870`
- `0x180010b3c`
- `0x18001155c`
- `0x180011a28`
- `0x180011cc0`
- `0x180013d28`
- `0x180013ffc`
- `0x18001486c`
- `0x1800156ae`
- `0x1800156e3`
- `0x180015880`
- `0x180015892`
- `0x180015dde`
- `0x180015f2d`
- `0x18001609a`
- `0x1800162cc`
- `0x180016302`
- `0x180016326`
- `0x18001635c`
- `0x18001636e`
- `0x1800163ec`
- `0x180016422`
- `0x180016434`
- `0x180016458`
- `0x18001646a`
- `0x180016578`
- `0x1800166da`
- `0x1800166f0`
- `0x18001686a`

## callees

- `0x180001bb4`
- `0x180004274`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(char **a1)
{
  unsigned __int64 v1; // rdx
  char *v3; // rax
  char *v4; // rcx
  __int64 result; // rax

  v1 = (unsigned __int64)a1[3];
  if ( v1 > 7 )
  {
    v3 = *a1;
    if ( 2 * v1 + 2 < 0x1000 )
    {
      v4 = *a1;
    }
    else
    {
      v4 = (char *)*((_QWORD *)v3 - 1);
      if ( (unsigned __int64)(v3 - v4 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v4);
  }
  result = 0;
  a1[3] = (char *)7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180004274  push    rbx
0x180004276  sub     rsp, 20h
0x18000427a  mov     rdx, [rcx+18h]
0x18000427e  mov     rbx, rcx
0x180004281  cmp     rdx, 7
0x180004285  jbe     short loc_1800042C1
0x180004287  mov     rax, [rcx]
0x18000428a  lea     rdx, ds:2[rdx*2]
0x180004292  cmp     rdx, 1000h
0x180004299  jb      short loc_1800042B9
0x18000429b  mov     rcx, [rax-8]
0x18000429f  sub     rax, rcx
0x1800042a2  sub     rax, 8
0x1800042a6  cmp     rax, 1Fh
0x1800042aa  ja      short loc_1800042B2
0x1800042ac  add     rdx, 27h ; '''
0x1800042b0  jmp     short loc_1800042BC
0x1800042b2  mov     ecx, 5
0x1800042b7  int     29h; Win8: RtlFailFast(ecx)
0x1800042b9  mov     rcx, rax; Block
0x1800042bc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800042c1  xor     eax, eax
0x1800042c3  mov     qword ptr [rbx+18h], 7
0x1800042cb  mov     [rbx+10h], rax
0x1800042cf  mov     [rbx], ax
0x1800042d2  add     rsp, 20h
0x1800042d6  pop     rbx
0x1800042d7  retn
```
