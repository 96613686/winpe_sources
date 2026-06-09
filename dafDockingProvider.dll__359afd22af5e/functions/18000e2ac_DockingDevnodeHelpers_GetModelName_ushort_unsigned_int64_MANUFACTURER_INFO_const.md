# DockingDevnodeHelpers::GetModelName(ushort *,unsigned __int64,_MANUFACTURER_INFO const &)

- ea: `0x18000e2ac`
- end: `0x18000e33d`
- name: `?GetModelName@DockingDevnodeHelpers@@SAXPEAG_KAEBU_MANUFACTURER_INFO@@@Z`
- size: `145`
- prototype: `void __fastcall(unsigned __int16 *Destination, __int64, const struct _MANUFACTURER_INFO *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180009660`
- `0x18000ee64`
- `0x18000f3ec`
- `0x180012ddc`
- `0x180018be0`

## callees

- `0x1800073d8`
- `0x18000e2ac`
- `0x180010254`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000e331`
- `msvcrt!memcpy_s` at `0x18000e331`

## pseudocode

```c
void __fastcall DockingDevnodeHelpers::GetModelName(
        unsigned __int16 *Destination,
        __int64 a2,
        const struct _MANUFACTURER_INFO *a3)
{
  int v4; // eax

  v4 = StringCchPrintfW(Destination, 0x12Fu, L"%s %s %s", a3, (char *)a3 + 400, (char *)a3 + 200);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        57,
        &WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids,
        (unsigned int)v4);
    }
    memcpy_s(Destination, 0x25Eu, L"<Error!>", 0x12u);
  }
}

```

## disassembly

```asm
0x18000e2ac  push    rbx
0x18000e2ae  sub     rsp, 30h
0x18000e2b2  lea     rdx, [r8+190h]
0x18000e2b9  mov     r9, r8
0x18000e2bc  lea     rax, [r8+0C8h]
0x18000e2c3  mov     rbx, rcx
0x18000e2c6  mov     [rsp+38h+var_10], rax
0x18000e2cb  lea     r8, aSSS; "%s %s %s"
0x18000e2d2  mov     [rsp+38h+var_18], rdx
0x18000e2d7  mov     edx, 12Fh; unsigned __int64
0x18000e2dc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e2e1  test    eax, eax
0x18000e2e3  jns     short loc_18000E337
0x18000e2e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2ec  lea     rdx, WPP_GLOBAL_Control
0x18000e2f3  cmp     rcx, rdx
0x18000e2f6  jz      short loc_18000E31C
0x18000e2f8  cmp     byte ptr [rcx+19h], 1
0x18000e2fc  jb      short loc_18000E31C
0x18000e2fe  test    byte ptr [rcx+1Ch], 1
0x18000e302  jz      short loc_18000E31C
0x18000e304  mov     rcx, [rcx+10h]
0x18000e308  lea     r8, WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids
0x18000e30f  mov     edx, 39h ; '9'
0x18000e314  mov     r9d, eax
0x18000e317  call    WPP_SF_d
0x18000e31c  mov     r9d, 12h; SourceSize
0x18000e322  lea     r8, aError; "<Error!>"
0x18000e329  mov     edx, 25Eh; DestinationSize
0x18000e32e  mov     rcx, rbx; Destination
0x18000e331  call    cs:__imp_memcpy_s
0x18000e337  add     rsp, 30h
0x18000e33b  pop     rbx
0x18000e33c  retn
```
