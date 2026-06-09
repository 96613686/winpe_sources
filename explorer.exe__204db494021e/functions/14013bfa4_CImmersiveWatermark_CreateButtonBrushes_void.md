# CImmersiveWatermark::_CreateButtonBrushes(void)

- ea: `0x14013bfa4`
- end: `0x14013c115`
- name: `?_CreateButtonBrushes@CImmersiveWatermark@@AEAAJXZ`
- size: `369`
- prototype: `__int64 __fastcall(CImmersiveWatermark *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14002fe6c`

## callees

- `0x140048e38`
- `0x1400b1a78`
- `0x14013bfa4`

## import_xrefs

- `GDI32!CreatePen` at `0x14013c06a`
- `GDI32!CreatePen` at `0x14013c0a2`
- `GDI32!CreatePen` at `0x14013c0da`
- `GDI32!CreatePen` at `0x14013c06a`
- `GDI32!CreatePen` at `0x14013c0a2`
- `GDI32!CreatePen` at `0x14013c0da`
- `GDI32!CreateSolidBrush` at `0x14013bfc3`
- `GDI32!CreateSolidBrush` at `0x14013bffb`
- `GDI32!CreateSolidBrush` at `0x14013c02e`
- `GDI32!CreateSolidBrush` at `0x14013bfc3`
- `GDI32!CreateSolidBrush` at `0x14013bffb`
- `GDI32!CreateSolidBrush` at `0x14013c02e`

## pseudocode

```c
__int64 __fastcall CImmersiveWatermark::_CreateButtonBrushes(CImmersiveWatermark *this)
{
  __int64 Color; // rax
  HBRUSH SolidBrush; // rax
  unsigned int v4; // ebx
  __int64 v5; // rax
  HBRUSH v6; // rax
  __int64 v7; // rax
  HBRUSH v8; // rax
  __int64 v9; // rax
  HPEN Pen; // rax
  __int64 v11; // rax
  HPEN v12; // rax
  __int64 v13; // rax
  HPEN v14; // rax

  Color = CImmersiveColor::GetColor(1019);
  SolidBrush = CreateSolidBrush(Color & 0xFFFFFF);
  *((_QWORD *)this + 8) = SolidBrush;
  v4 = SolidBrush == 0 ? 0x80004005 : 0;
  if ( !SolidBrush )
    goto LABEL_8;
  v5 = CImmersiveColor::GetColor(1017);
  v6 = CreateSolidBrush(v5 & 0xFFFFFF);
  *((_QWORD *)this + 9) = v6;
  v4 = v6 == 0 ? 0x80004005 : 0;
  if ( !v6 )
    goto LABEL_8;
  v7 = CImmersiveColor::GetColor(1018);
  v8 = CreateSolidBrush(v7 & 0xFFFFFF);
  *((_QWORD *)this + 10) = v8;
  v4 = v8 == 0 ? 0x80004005 : 0;
  if ( !v8 )
    goto LABEL_8;
  v9 = CImmersiveColor::GetColor(1025);
  Pen = CreatePen(6, 2, v9 & 0xFFFFFF);
  *((_QWORD *)this + 12) = Pen;
  v4 = Pen == 0 ? 0x80004005 : 0;
  if ( !Pen )
    goto LABEL_8;
  v11 = CImmersiveColor::GetColor(1026);
  v12 = CreatePen(6, 2, v11 & 0xFFFFFF);
  *((_QWORD *)this + 11) = v12;
  v4 = v12 == 0 ? 0x80004005 : 0;
  if ( !v12 )
    goto LABEL_8;
  v13 = CImmersiveColor::GetColor(1027);
  v14 = CreatePen(6, 2, v13 & 0xFFFFFF);
  *((_QWORD *)this + 13) = v14;
  v4 = v14 == 0 ? 0x80004005 : 0;
  if ( v14 )
    *((_BYTE *)this + 112) = 1;
  else
LABEL_8:
    CImmersiveWatermark::_DeleteButtonBrushes(this);
  return v4;
}

```

## disassembly

```asm
0x14013bfa4  push    rbx
0x14013bfa6  push    rbp
0x14013bfa7  push    rsi
0x14013bfa8  push    rdi
0x14013bfa9  sub     rsp, 28h
0x14013bfad  mov     rdi, rcx
0x14013bfb0  mov     ecx, 3FBh
0x14013bfb5  call    ?GetColor@CImmersiveColor@@SAKW4IMMERSIVE_COLOR_TYPE@@@Z; CImmersiveColor::GetColor(IMMERSIVE_COLOR_TYPE)
0x14013bfba  mov     esi, 0FFFFFFh
0x14013bfbf  and     eax, esi
0x14013bfc1  mov     ecx, eax; color
0x14013bfc3  call    cs:__imp_CreateSolidBrush
0x14013bfca  nop     dword ptr [rax+rax+00h]
0x14013bfcf  mov     rdx, rax
0x14013bfd2  mov     [rdi+40h], rax
0x14013bfd6  neg     rdx
0x14013bfd9  mov     ebp, 80004005h
0x14013bfde  sbb     ebx, ebx
0x14013bfe0  not     ebx
0x14013bfe2  and     ebx, ebp
0x14013bfe4  test    rax, rax
0x14013bfe7  jz      loc_14013C101
0x14013bfed  mov     ecx, 3F9h
0x14013bff2  call    ?GetColor@CImmersiveColor@@SAKW4IMMERSIVE_COLOR_TYPE@@@Z; CImmersiveColor::GetColor(IMMERSIVE_COLOR_TYPE)
0x14013bff7  and     eax, esi
0x14013bff9  mov     ecx, eax; color
0x14013bffb  call    cs:__imp_CreateSolidBrush
0x14013c002  nop     dword ptr [rax+rax+00h]
0x14013c007  mov     rcx, rax
0x14013c00a  mov     [rdi+48h], rax
0x14013c00e  neg     rcx
0x14013c011  sbb     ebx, ebx
0x14013c013  not     ebx
0x14013c015  and     ebx, ebp
0x14013c017  test    rax, rax
0x14013c01a  jz      loc_14013C101
0x14013c020  mov     ecx, 3FAh
0x14013c025  call    ?GetColor@CImmersiveColor@@SAKW4IMMERSIVE_COLOR_TYPE@@@Z; CImmersiveColor::GetColor(IMMERSIVE_COLOR_TYPE)
0x14013c02a  and     eax, esi
0x14013c02c  mov     ecx, eax; color
0x14013c02e  call    cs:__imp_CreateSolidBrush
0x14013c035  nop     dword ptr [rax+rax+00h]
0x14013c03a  mov     rcx, rax
0x14013c03d  mov     [rdi+50h], rax
0x14013c041  neg     rcx
0x14013c044  sbb     ebx, ebx
0x14013c046  not     ebx
0x14013c048  and     ebx, ebp
0x14013c04a  test    rax, rax
0x14013c04d  jz      loc_14013C101
0x14013c053  mov     ecx, 401h
0x14013c058  call    ?GetColor@CImmersiveColor@@SAKW4IMMERSIVE_COLOR_TYPE@@@Z; CImmersiveColor::GetColor(IMMERSIVE_COLOR_TYPE)
0x14013c05d  mov     edx, 2; cWidth
0x14013c062  and     eax, esi
0x14013c064  mov     r8d, eax; color
0x14013c067  lea     ecx, [rdx+4]; iStyle
0x14013c06a  call    cs:__imp_CreatePen
0x14013c071  nop     dword ptr [rax+rax+00h]
0x14013c076  mov     rcx, rax
0x14013c079  mov     [rdi+60h], rax
0x14013c07d  neg     rcx
0x14013c080  sbb     ebx, ebx
0x14013c082  not     ebx
0x14013c084  and     ebx, ebp
0x14013c086  test    rax, rax
0x14013c089  jz      short loc_14013C101
0x14013c08b  mov     ecx, 402h
0x14013c090  call    ?GetColor@CImmersiveColor@@SAKW4IMMERSIVE_COLOR_TYPE@@@Z; CImmersiveColor::GetColor(IMMERSIVE_COLOR_TYPE)
0x14013c095  mov     edx, 2; cWidth
0x14013c09a  and     eax, esi
0x14013c09c  mov     r8d, eax; color
0x14013c09f  lea     ecx, [rdx+4]; iStyle
0x14013c0a2  call    cs:__imp_CreatePen
0x14013c0a9  nop     dword ptr [rax+rax+00h]
0x14013c0ae  mov     rcx, rax
0x14013c0b1  mov     [rdi+58h], rax
0x14013c0b5  neg     rcx
0x14013c0b8  sbb     ebx, ebx
0x14013c0ba  not     ebx
0x14013c0bc  and     ebx, ebp
0x14013c0be  test    rax, rax
0x14013c0c1  jz      short loc_14013C101
0x14013c0c3  mov     ecx, 403h
0x14013c0c8  call    ?GetColor@CImmersiveColor@@SAKW4IMMERSIVE_COLOR_TYPE@@@Z; CImmersiveColor::GetColor(IMMERSIVE_COLOR_TYPE)
0x14013c0cd  mov     edx, 2; cWidth
0x14013c0d2  and     eax, esi
0x14013c0d4  mov     r8d, eax; color
0x14013c0d7  lea     ecx, [rdx+4]; iStyle
0x14013c0da  call    cs:__imp_CreatePen
0x14013c0e1  nop     dword ptr [rax+rax+00h]
0x14013c0e6  mov     rcx, rax
0x14013c0e9  mov     [rdi+68h], rax
0x14013c0ed  neg     rcx
0x14013c0f0  sbb     ebx, ebx
0x14013c0f2  not     ebx
0x14013c0f4  and     ebx, ebp
0x14013c0f6  test    rax, rax
0x14013c0f9  jz      short loc_14013C101
0x14013c0fb  mov     byte ptr [rdi+70h], 1
0x14013c0ff  jmp     short loc_14013C109
0x14013c101  mov     rcx, rdi; this
0x14013c104  call    ?_DeleteButtonBrushes@CImmersiveWatermark@@AEAAXXZ; CImmersiveWatermark::_DeleteButtonBrushes(void)
0x14013c109  mov     eax, ebx
0x14013c10b  add     rsp, 28h
0x14013c10f  pop     rdi
0x14013c110  pop     rsi
0x14013c111  pop     rbp
0x14013c112  pop     rbx
0x14013c113  retn
```
