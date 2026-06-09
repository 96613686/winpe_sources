# CPath::~CPath(void)

- ea: `0x1800046c0`
- end: `0x180004769`
- name: `??1CPath@@QEAA@XZ`
- size: `169`
- prototype: `void __fastcall(CPath *__hidden this)`
- caller_count: `12`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003ca0`
- `0x180004028`
- `0x180004270`
- `0x18000df30`
- `0x180010400`
- `0x18001057c`
- `0x180010834`
- `0x180010934`
- `0x180010ae8`
- `0x180010c64`
- `0x180012638`
- `0x180025fe4`

## callees

- `0x1800046c0`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180004761`
- `ntdll!RtlFreeUnicodeString` at `0x180004761`

## pseudocode

```c
void __fastcall CPath::~CPath(WCHAR **this)
{
  _WORD *v1; // rdi
  WCHAR **v3; // rsi
  WCHAR *v4; // rax
  WCHAR *v5; // rcx
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-18h] BYREF

  v1 = this + 65;
  if ( this != (WCHAR **)-520LL )
  {
    v3 = this + 67;
    if ( this != (WCHAR **)-536LL )
    {
      v4 = *v3;
      if ( *v3 )
      {
        if ( v4 != this[68] )
        {
          *(_QWORD *)&UnicodeString.Length = 0;
          UnicodeString.Buffer = v4;
          RtlFreeUnicodeString(&UnicodeString);
        }
        *v3 = this[68];
        this[69] = this[70];
      }
    }
    v5 = this[68];
    this[66] = v5;
    if ( v5 )
      *v5 = 0;
    *v1 = 0;
    *((_WORD *)this + 261) = *((_WORD *)this + 280);
  }
}

```

## disassembly

```asm
0x1800046c0  mov     [rsp+arg_8], rbx
0x1800046c5  push    rdi
0x1800046c6  sub     rsp, 30h
0x1800046ca  lea     rdi, [rcx+208h]
0x1800046d1  mov     rbx, rcx
0x1800046d4  test    rdi, rdi
0x1800046d7  jz      short loc_180004743
0x1800046d9  mov     [rsp+38h+arg_0], rsi
0x1800046de  lea     rsi, [rcx+218h]
0x1800046e5  test    rsi, rsi
0x1800046e8  jz      short loc_180004713
0x1800046ea  mov     rax, [rsi]
0x1800046ed  test    rax, rax
0x1800046f0  jz      short loc_180004713
0x1800046f2  cmp     rax, [rcx+220h]
0x1800046f9  jnz     short loc_18000474E
0x1800046fb  mov     rax, [rbx+220h]
0x180004702  mov     [rsi], rax
0x180004705  mov     rax, [rbx+230h]
0x18000470c  mov     [rbx+228h], rax
0x180004713  mov     rcx, [rbx+220h]
0x18000471a  mov     rsi, [rsp+38h+arg_0]
0x18000471f  mov     [rbx+210h], rcx
0x180004726  test    rcx, rcx
0x180004729  jz      short loc_180004730
0x18000472b  xor     eax, eax
0x18000472d  mov     [rcx], ax
0x180004730  xor     eax, eax
0x180004732  mov     [rdi], ax
0x180004735  movzx   eax, word ptr [rbx+230h]
0x18000473c  mov     [rbx+20Ah], ax
0x180004743  mov     rbx, [rsp+38h+arg_8]
0x180004748  add     rsp, 30h
0x18000474c  pop     rdi
0x18000474d  retn
0x18000474e  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x180004753  mov     qword ptr [rsp+38h+UnicodeString.Length], 0
0x18000475c  mov     [rsp+38h+UnicodeString.Buffer], rax
0x180004761  call    cs:__imp_RtlFreeUnicodeString
0x180004767  jmp     short loc_1800046FB
```
