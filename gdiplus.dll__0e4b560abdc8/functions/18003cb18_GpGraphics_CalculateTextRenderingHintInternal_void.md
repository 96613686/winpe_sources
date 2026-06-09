# GpGraphics::CalculateTextRenderingHintInternal(void)

- ea: `0x18003cb18`
- end: `0x18003cc82`
- name: `?CalculateTextRenderingHintInternal@GpGraphics@@IEAAXXZ`
- size: `362`
- prototype: `void __fastcall(GpGraphics *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800377b0`
- `0x18003c3c4`
- `0x18003c718`
- `0x1800c7970`

## callees

- `0x18003cb18`
- `0x1801130cc`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x18003cb77`
- `USER32!GetSystemMetrics` at `0x18003cb77`
- `USER32!SystemParametersInfoW` at `0x18003cc04`
- `USER32!SystemParametersInfoW` at `0x18003cc36`
- `USER32!SystemParametersInfoW` at `0x18003cc04`
- `USER32!SystemParametersInfoW` at `0x18003cc36`

## pseudocode

```c
void __fastcall GpGraphics::CalculateTextRenderingHintInternal(GpGraphics *this)
{
  int v2; // ebx
  __int64 v3; // rax
  DpBitmap *v4; // rax
  int pvParam; // [rsp+30h] [rbp+8h] BYREF
  int v6; // [rsp+38h] [rbp+10h] BYREF

  v2 = *(_DWORD *)(*((_QWORD *)this + 17) + 24LL);
  if ( *((_DWORD *)this + 16) )
    goto LABEL_19;
  if ( !v2 )
  {
    if ( Globals::CurrentSystemRenderingHintInvalid )
    {
      pvParam = 0;
      v6 = 0;
      SystemParametersInfoW(0x4Au, 0, &pvParam, 0);
      if ( pvParam )
      {
        SystemParametersInfoW(0x200Au, 0, &v6, 0);
        v2 = (v6 & 2) != 0 ? 5 : 3;
      }
      else
      {
        v2 = 1;
      }
      Globals::CurrentSystemRenderingHint = v2;
    }
    else
    {
      v2 = Globals::CurrentSystemRenderingHint;
    }
  }
  if ( v2 == 5 )
  {
    if ( Globals::OsVer.dwMajorVersion < 5 || Globals::OsVer.dwMajorVersion == 5 && !Globals::OsVer.dwMinorVersion )
    {
LABEL_19:
      v2 = 1;
      goto LABEL_10;
    }
  }
  else if ( v2 != 4 && v2 != 3 )
  {
    goto LABEL_10;
  }
  v3 = *((_QWORD *)this + 5);
  if ( v3 && (*(_DWORD *)(v3 + 12) & 0xFF00u) <= 0x800 && *(_DWORD *)(v3 + 12) != 0x10000000 )
    goto LABEL_19;
  if ( GetSystemMetrics(4096) )
  {
    v4 = (DpBitmap *)*((_QWORD *)this + 5);
    if ( v4 )
    {
      if ( v4 == Globals::DesktopSurface )
        goto LABEL_19;
    }
  }
  if ( Globals::CurrentSystemRenderingHintInvalid && v2 == 5 )
    UpdateLCDOrientation();
LABEL_10:
  Globals::CurrentSystemRenderingHintInvalid = 0;
  *((_DWORD *)this + 242) = v2;
}

```

## disassembly

```asm
0x18003cb18  mov     [rsp+arg_10], rbx
0x18003cb1d  push    rsi
0x18003cb1e  sub     rsp, 20h
0x18003cb22  cmp     dword ptr [rcx+40h], 0
0x18003cb26  mov     rsi, rcx
0x18003cb29  mov     rax, [rcx+88h]
0x18003cb30  mov     ebx, [rax+18h]
0x18003cb33  jnz     loc_18003CBE6
0x18003cb39  test    ebx, ebx
0x18003cb3b  jz      short loc_18003CBB9
0x18003cb3d  cmp     ebx, 5
0x18003cb40  jnz     loc_18003CBCD
0x18003cb46  cmp     cs:?OsVer@Globals@@3U_OSVERSIONINFOA@@A.dwMajorVersion, ebx; _OSVERSIONINFOA Globals::OsVer ...
0x18003cb4c  jb      loc_18003CBE6
0x18003cb52  jz      loc_18003CC54
0x18003cb58  mov     rax, [rsi+28h]
0x18003cb5c  test    rax, rax
0x18003cb5f  jz      short loc_18003CB72
0x18003cb61  mov     ecx, [rax+0Ch]
0x18003cb64  mov     eax, ecx
0x18003cb66  and     eax, 0FF00h
0x18003cb6b  cmp     eax, 800h
0x18003cb70  jbe     short loc_18003CBDE
0x18003cb72  mov     ecx, 1000h; nIndex
0x18003cb77  call    cs:__imp_GetSystemMetrics
0x18003cb7e  nop     dword ptr [rax+rax+00h]
0x18003cb83  test    eax, eax
0x18003cb85  jnz     loc_18003CC63
0x18003cb8b  cmp     cs:?CurrentSystemRenderingHintInvalid@Globals@@3HA, 0; int Globals::CurrentSystemRenderingHintInvalid
0x18003cb92  jnz     short loc_18003CBAD
0x18003cb94  and     cs:?CurrentSystemRenderingHintInvalid@Globals@@3HA, 0; int Globals::CurrentSystemRenderingHintInvalid
0x18003cb9b  mov     [rsi+3C8h], ebx
0x18003cba1  mov     rbx, [rsp+28h+arg_10]
0x18003cba6  add     rsp, 20h
0x18003cbaa  pop     rsi
0x18003cbab  retn
0x18003cbad  cmp     ebx, 5
0x18003cbb0  jnz     short loc_18003CB94
0x18003cbb2  call    ?UpdateLCDOrientation@@YAXXZ; UpdateLCDOrientation(void)
0x18003cbb7  jmp     short loc_18003CB94
0x18003cbb9  cmp     cs:?CurrentSystemRenderingHintInvalid@Globals@@3HA, 0; int Globals::CurrentSystemRenderingHintInvalid
0x18003cbc0  jnz     short loc_18003CBED
0x18003cbc2  mov     ebx, cs:?CurrentSystemRenderingHint@Globals@@3W4TextRenderingHint@@A; TextRenderingHint Globals::CurrentSystemRenderingHint
0x18003cbc8  jmp     loc_18003CB3D
0x18003cbcd  mov     eax, ebx
0x18003cbcf  cmp     ebx, 4
0x18003cbd2  jz      short loc_18003CB58
0x18003cbd4  cmp     eax, 3
0x18003cbd7  jnz     short loc_18003CB94
0x18003cbd9  jmp     loc_18003CB58
0x18003cbde  cmp     ecx, 10000000h
0x18003cbe4  jz      short loc_18003CB72
0x18003cbe6  mov     ebx, 1
0x18003cbeb  jmp     short loc_18003CB94
0x18003cbed  and     [rsp+28h+pvParam], 0
0x18003cbf2  lea     r8, [rsp+28h+pvParam]; pvParam
0x18003cbf7  and     [rsp+28h+arg_8], 0
0x18003cbfc  xor     edx, edx; uiParam
0x18003cbfe  xor     r9d, r9d; fWinIni
0x18003cc01  lea     ecx, [rdx+4Ah]; uiAction
0x18003cc04  call    cs:__imp_SystemParametersInfoW
0x18003cc0b  nop     dword ptr [rax+rax+00h]
0x18003cc10  cmp     [rsp+28h+pvParam], 0
0x18003cc15  jnz     short loc_18003CC27
0x18003cc17  mov     ebx, 1
0x18003cc1c  mov     cs:?CurrentSystemRenderingHint@Globals@@3W4TextRenderingHint@@A, ebx; TextRenderingHint Globals::CurrentSystemRenderingHint
0x18003cc22  jmp     loc_18003CB3D
0x18003cc27  xor     r9d, r9d; fWinIni
0x18003cc2a  lea     r8, [rsp+28h+arg_8]; pvParam
0x18003cc2f  xor     edx, edx; uiParam
0x18003cc31  mov     ecx, 200Ah; uiAction
0x18003cc36  call    cs:__imp_SystemParametersInfoW
0x18003cc3d  nop     dword ptr [rax+rax+00h]
0x18003cc42  mov     eax, [rsp+28h+arg_8]
0x18003cc46  and     al, 2
0x18003cc48  neg     al
0x18003cc4a  sbb     ebx, ebx
0x18003cc4c  and     ebx, 2
0x18003cc4f  add     ebx, 3
0x18003cc52  jmp     short loc_18003CC1C
0x18003cc54  cmp     cs:?OsVer@Globals@@3U_OSVERSIONINFOA@@A.dwMinorVersion, 1; _OSVERSIONINFOA Globals::OsVer ...
0x18003cc5b  jnb     loc_18003CB58
0x18003cc61  jmp     short loc_18003CBE6
0x18003cc63  mov     rax, [rsi+28h]
0x18003cc67  test    rax, rax
0x18003cc6a  jz      loc_18003CB8B
0x18003cc70  cmp     rax, cs:?DesktopSurface@Globals@@3PEAVDpBitmap@@EA; DpBitmap * Globals::DesktopSurface
0x18003cc77  jz      loc_18003CBE6
0x18003cc7d  jmp     loc_18003CB8B
```
