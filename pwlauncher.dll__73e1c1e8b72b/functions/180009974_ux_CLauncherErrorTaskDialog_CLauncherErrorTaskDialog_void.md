# ux::CLauncherErrorTaskDialog::~CLauncherErrorTaskDialog(void)

- ea: `0x180009974`
- end: `0x1800099b5`
- name: `??1CLauncherErrorTaskDialog@ux@@UEAA@XZ`
- size: `65`
- prototype: `void __fastcall(ux::CLauncherErrorTaskDialog *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180008e20`
- `0x180009ba0`
- `0x18000ae20`
- `0x18000aed8`
- `0x18001034c`
- `0x18001035e`
- `0x1800107cd`

## callees

- `0x180008ac8`
- `0x180009974`

## pseudocode

```c
void __fastcall ux::CLauncherErrorTaskDialog::~CLauncherErrorTaskDialog(ux::CLauncherErrorTaskDialog *this)
{
  *(_QWORD *)this = &ux::CLauncherErrorTaskDialog::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids);
}

```

## disassembly

```asm
0x180009974  sub     rsp, 28h
0x180009978  lea     rax, ??_7CLauncherErrorTaskDialog@ux@@6B@; const ux::CLauncherErrorTaskDialog::`vftable'
0x18000997f  mov     [rcx], rax
0x180009982  mov     rcx, cs:WPP_GLOBAL_Control
0x180009989  lea     rax, WPP_GLOBAL_Control
0x180009990  cmp     rcx, rax
0x180009993  jz      short loc_1800099B0
0x180009995  test    byte ptr [rcx+1Ch], 8
0x180009999  jz      short loc_1800099B0
0x18000999b  mov     rcx, [rcx+10h]
0x18000999f  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x1800099a6  mov     edx, 28h ; '('
0x1800099ab  call    WPP_SF_
0x1800099b0  add     rsp, 28h
0x1800099b4  retn
```
