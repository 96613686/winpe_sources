# DWMCursorBroker::CreateMotionTransformAndVerifySend(DWMCursor *,uint)

- ea: `0x1800c70d0`
- end: `0x1800c72cc`
- name: `?CreateMotionTransformAndVerifySend@DWMCursorBroker@@AEAAJPEAVDWMCursor@@I@Z`
- size: `508`
- prototype: `__int64 __fastcall(DWMCursorBroker *__hidden this, struct DWMCursor *, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180087750`
- `0x1800c6fd0`

## callees

- `0x18008ead4`
- `0x18008ee44`
- `0x1800af9b8`
- `0x1800c70d0`
- `0x1800c73ac`
- `0x1800d918c`
- `0x1800f08d8`
- `0x1801ce010`

## import_xrefs

- `win32u!NtDCompositionDuplicateHandleToProcess` at `0x1800c71b5`
- `win32u!NtDCompositionDuplicateHandleToProcess` at `0x1800c71b5`

## string_xrefs

- `0x1800c7190`: `onecoreuap\windows\moderncore\inputv2\systeminputrouters\dwm\components\cursor\lib\dwmcursor.cpp`
- `0x1800c71c7`: `onecoreuap\windows\moderncore\inputv2\systeminputrouters\dwm\components\cursor\lib\dwmcursor.cpp`
- `0x1800c71e9`: `onecoreuap\windows\moderncore\inputv2\systeminputrouters\dwm\components\cursor\lib\dwmcursorbroker.cpp`
- `0x1800c7224`: `onecoreuap\windows\moderncore\inputv2\systeminputrouters\dwm\components\cursor\lib\dwmcursorbroker.cpp`
- `0x1800c7295`: `onecoreuap\windows\moderncore\inputv2\systeminputrouters\dwm\components\cursor\lib\dwmcursorbroker.cpp`

## pseudocode

```c
__int64 __fastcall DWMCursorBroker::CreateMotionTransformAndVerifySend(
        DWMCursorBroker *this,
        struct DWMCursor *a2,
        unsigned int a3)
{
  __int64 v3; // rbx
  __int64 v6; // rbp
  __int64 v7; // rcx
  __int64 v8; // rax
  unsigned int v9; // r14d
  int v10; // eax
  int v11; // ebx
  int v12; // eax
  int v14; // eax
  int v15; // ebx
  int v16; // [rsp+20h] [rbp-68h]
  int v17; // [rsp+20h] [rbp-68h]
  _BYTE v18[4]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v19; // [rsp+34h] [rbp-54h]
  int v20; // [rsp+40h] [rbp-48h]
  int v21; // [rsp+44h] [rbp-44h]
  __int64 v22; // [rsp+48h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  __int64 v24; // [rsp+90h] [rbp+8h] BYREF

  v3 = a3;
  v6 = 3LL * a3;
  if ( *((_QWORD *)this + 3 * a3 + 27) )
  {
    memset_0(v18, 0, 0x40u);
    v7 = *(_QWORD *)(*(__int64 (__fastcall **)(struct DWMCursor *, __int64 *))(*(_QWORD *)a2 + 48LL))(a2, &v24);
    v8 = *(_QWORD *)a2;
    v19 = v7;
    v20 = (*(__int64 (__fastcall **)(struct DWMCursor *))(v8 + 56))(a2);
    v21 = (*(__int64 (__fastcall **)(struct DWMCursor *))(*(_QWORD *)a2 + 64LL))(a2);
    if ( *((_BYTE *)this + 24 * v3 + 224) )
    {
      v9 = *((_DWORD *)this + 6 * v3 + 52);
      v24 = 0;
      v10 = DWMCursor::EnsureDCompTransform(a2);
      v11 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD6,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\components\\cursor\\lib\\dwmcursor.cpp",
          (const char *)(unsigned int)v10,
          v16);
LABEL_7:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x19D,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\components\\cursor\\lib\\dwmcursorbroker.cpp",
          (const char *)(unsigned int)v11,
          v17);
        return (unsigned int)v11;
      }
      v12 = NtDCompositionDuplicateHandleToProcess(*((_QWORD *)a2 + 8), v9, &v24);
      if ( v12 < 0 )
      {
        v11 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0xDA,
                (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\components\\cursor\\lib\\dwmcursor.cpp",
                (const char *)(unsigned int)v12,
                v16);
        if ( v11 < 0 )
          goto LABEL_7;
      }
      v22 = v24;
    }
    else
    {
      v14 = DWMCursor::EnsureDwmCursorController(a2);
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1A5,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\components\\cursor\\lib\\dwmcursorbroker.cpp",
          (const char *)(unsigned int)v14,
          v16);
    }
    v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _BYTE *))(**((_QWORD **)this + 22) + 176LL))(
            *((_QWORD *)this + 22),
            *((_QWORD *)this + v6 + 27),
            4,
            v18);
    if ( v15 < 0 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 22) + 168LL))(
        *((_QWORD *)this + 22),
        *((_QWORD *)this + v6 + 27));
      *((_QWORD *)this + v6 + 27) = 0;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1B6,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\components\\cursor\\lib\\dwmcursorbroker.cpp",
        (const char *)(unsigned int)v15,
        64);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800c70d0  mov     [rsp+arg_8], rbx
0x1800c70d5  mov     [rsp+arg_10], rbp
0x1800c70da  push    rsi
0x1800c70db  push    rdi
0x1800c70dc  push    r14
0x1800c70de  sub     rsp, 70h
0x1800c70e2  mov     ebx, r8d
0x1800c70e5  mov     rsi, rdx
0x1800c70e8  mov     rdi, rcx
0x1800c70eb  lea     rbp, [rbx+rbx*2]
0x1800c70ef  cmp     qword ptr [rcx+rbp*8+0D8h], 0
0x1800c70f8  jz      loc_1800C72B5
0x1800c70fe  xor     edx, edx; Val
0x1800c7100  lea     rcx, [rsp+88h+var_58]; void *
0x1800c7105  lea     r8d, [rdx+40h]; Size
0x1800c7109  call    memset_0
0x1800c710e  mov     rax, [rsi]
0x1800c7111  lea     rdx, [rsp+88h+arg_0]
0x1800c7119  mov     rcx, rsi
0x1800c711c  mov     rax, [rax+30h]
0x1800c7120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7125  mov     rcx, [rax]
0x1800c7128  mov     rax, [rsi]
0x1800c712b  mov     [rsp+88h+var_54], rcx
0x1800c7130  mov     rcx, rsi
0x1800c7133  mov     rax, [rax+38h]
0x1800c7137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c713c  mov     [rsp+88h+var_48], eax
0x1800c7140  mov     rcx, rsi
0x1800c7143  mov     rax, [rsi]
0x1800c7146  mov     rax, [rax+40h]
0x1800c714a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c714f  lea     r14, [rbx+rbx*2]
0x1800c7153  mov     [rsp+88h+var_44], eax
0x1800c7157  cmp     byte ptr [rdi+r14*8+0E0h], 0
0x1800c7160  mov     rcx, rsi; this
0x1800c7163  jz      loc_1800C7213
0x1800c7169  mov     r14d, [rdi+r14*8+0D0h]
0x1800c7171  mov     [rsp+88h+arg_0], 0
0x1800c717d  call    ?EnsureDCompTransform@DWMCursor@@AEAAJXZ; DWMCursor::EnsureDCompTransform(void)
0x1800c7182  mov     ebx, eax
0x1800c7184  test    eax, eax
0x1800c7186  jns     short loc_1800C71A6
0x1800c7188  mov     rcx, [rsp+88h]; this
0x1800c7190  lea     r8, aOnecoreuapWind_53; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800c7197  mov     r9d, eax; char *
0x1800c719a  mov     edx, 0D6h; void *
0x1800c719f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c71a4  jmp     short loc_1800C71E1
0x1800c71a6  mov     rcx, [rsi+40h]
0x1800c71aa  lea     r8, [rsp+88h+arg_0]
0x1800c71b2  mov     edx, r14d
0x1800c71b5  call    cs:__imp_NtDCompositionDuplicateHandleToProcess
0x1800c71bb  test    eax, eax
0x1800c71bd  jns     short loc_1800C7204
0x1800c71bf  mov     rcx, [rsp+88h]; this
0x1800c71c7  lea     r8, aOnecoreuapWind_53; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800c71ce  mov     r9d, eax; char *
0x1800c71d1  mov     edx, 0DAh; void *
0x1800c71d6  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800c71db  mov     ebx, eax
0x1800c71dd  test    eax, eax
0x1800c71df  jns     short loc_1800C7204
0x1800c71e1  mov     rcx, [rsp+88h]; this
0x1800c71e9  lea     r8, aOnecoreuapWind_73; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800c71f0  mov     r9d, ebx; char *
0x1800c71f3  mov     edx, 19Dh; void *
0x1800c71f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c71fd  mov     eax, ebx
0x1800c71ff  jmp     loc_1800C72B7
0x1800c7204  mov     rax, [rsp+88h+arg_0]
0x1800c720c  mov     [rsp+88h+var_40], rax
0x1800c7211  jmp     short loc_1800C7238
0x1800c7213  call    ?EnsureDwmCursorController@DWMCursor@@QEAAJXZ; DWMCursor::EnsureDwmCursorController(void)
0x1800c7218  test    eax, eax
0x1800c721a  jns     short loc_1800C7238
0x1800c721c  mov     rcx, [rsp+88h]; this
0x1800c7224  lea     r8, aOnecoreuapWind_73; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800c722b  mov     r9d, eax; char *
0x1800c722e  mov     edx, 1A5h; void *
0x1800c7233  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c7238  mov     rcx, [rdi+0B0h]
0x1800c723f  lea     r9, [rsp+88h+var_58]
0x1800c7244  mov     rdx, [rdi+rbp*8+0D8h]
0x1800c724c  mov     r8d, 4
0x1800c7252  mov     [rsp+88h+var_68], 40h ; '@'; int
0x1800c725a  mov     rax, [rcx]
0x1800c725d  mov     rax, [rax+0B0h]
0x1800c7264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7269  mov     ebx, eax
0x1800c726b  test    eax, eax
0x1800c726d  jns     short loc_1800C72B5
0x1800c726f  mov     rcx, [rdi+0B0h]
0x1800c7276  mov     rdx, [rcx]
0x1800c7279  mov     rax, [rdx+0A8h]
0x1800c7280  mov     rdx, [rdi+rbp*8+0D8h]
0x1800c7288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c728d  mov     rcx, [rsp+88h]; this
0x1800c7295  lea     r8, aOnecoreuapWind_73; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800c729c  mov     r9d, ebx; char *
0x1800c729f  mov     qword ptr [rdi+rbp*8+0D8h], 0
0x1800c72ab  mov     edx, 1B6h; void *
0x1800c72b0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c72b5  xor     eax, eax
0x1800c72b7  lea     r11, [rsp+88h+var_18]
0x1800c72bc  mov     rbx, [r11+28h]
0x1800c72c0  mov     rbp, [r11+30h]
0x1800c72c4  mov     rsp, r11
0x1800c72c7  pop     r14
0x1800c72c9  pop     rdi
0x1800c72ca  pop     rsi
0x1800c72cb  retn
```
