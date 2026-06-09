# RefreshFormats

- ea: `0x180010548`
- end: `0x180010a73`
- name: `RefreshFormats`
- size: `1323`
- prototype: `__int64 __fastcall(DWORD_PTR dwInstance)`
- caller_count: `4`
- callee_count: `14`
- tags: ``

## callers

- `0x18000e608`
- `0x18000e7d4`
- `0x18000f330`
- `0x18000fba0`

## callees

- `0x180001940`
- `0x180008160`
- `0x180009270`
- `0x180009afa`
- `0x18000a250`
- `0x18000b8d0`
- `0x18000bca0`
- `0x18000ca28`
- `0x18000cfe0`
- `0x18000e268`
- `0x18000e520`
- `0x18000ef10`
- `0x180010548`
- `0x1800126b9`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800109e1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800109e1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001070c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001092d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001070c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001092d`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180010645`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180010888`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180010645`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180010888`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800106f1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180010703`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180010912`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180010924`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800106f1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180010703`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180010912`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180010924`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800106fa`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18001091b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800106fa`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18001091b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001064e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180010891`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001064e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180010891`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800105ab`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800105c8`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800109ad`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800109fb`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180010a10`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180010a3c`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800105ab`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800105c8`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800109ad`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800109fb`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180010a10`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180010a3c`
- `ext-ms-win-ntuser-window-l1-1-4!EnableWindow` at `0x180010a1c`
- `ext-ms-win-ntuser-window-l1-1-4!EnableWindow` at `0x180010a28`
- `ext-ms-win-ntuser-window-l1-1-4!EnableWindow` at `0x180010a1c`
- `ext-ms-win-ntuser-window-l1-1-4!EnableWindow` at `0x180010a28`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorW` at `0x18001058b`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorW` at `0x18001058b`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!SetCursor` at `0x180010594`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!SetCursor` at `0x180010a45`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!SetCursor` at `0x180010594`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!SetCursor` at `0x180010a45`

## pseudocode

```c
HCURSOR __fastcall RefreshFormats(DWORD_PTR dwInstance)
{
  HCURSOR result; // rax
  HCURSOR CursorW; // rax
  HCURSOR v4; // r15
  BOOL v5; // edi
  DWORD cbwfx; // ecx
  HGLOBAL v7; // rax
  struct tWAVEFORMATEX *v8; // rax
  struct tWAVEFORMATEX *v9; // r14
  __int64 v10; // rcx
  LPWAVEFORMATEX pwfx; // r8
  const void *v12; // rdx
  DWORD v13; // eax
  DWORD fdwEnum; // ecx
  HGLOBAL v15; // rax
  HGLOBAL v16; // rax
  __int64 v17; // rdx
  _WORD *v18; // rax
  __int64 v19; // rdx
  _WORD *v20; // rax
  DWORD v21; // ecx
  HGLOBAL v22; // rax
  struct tWAVEFORMATEX *v23; // rax
  struct tWAVEFORMATEX *v24; // r14
  __int64 v25; // rcx
  LPWAVEFORMATEX v26; // r8
  DWORD *v27; // rdx
  DWORD v28; // ecx
  HGLOBAL v29; // rax
  HGLOBAL v30; // rax
  __int64 v31; // rcx
  int v32; // eax
  struct tACMFORMATDETAILSW pafd; // [rsp+30h] [rbp-D0h] BYREF

  result = (HCURSOR)IsSendMessageWPresent();
  if ( (_BYTE)result )
  {
    CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
    v4 = SetCursor(CursorW);
    SendMessageW(*(HWND *)(dwInstance + 40), 0xBu, 0, 0);
    EmptyFormats(dwInstance);
    SendMessageW(*(HWND *)(dwInstance + 40), 0x14Bu, 0, 0);
    if ( !*(_DWORD *)(dwInstance + 200) )
    {
LABEL_48:
      v5 = 0;
      goto LABEL_49;
    }
    if ( *(_DWORD *)dwInstance )
    {
      if ( *(_DWORD *)dwInstance != 1 )
        goto LABEL_46;
      memset_0(&pafd, 0, sizeof(pafd));
      v5 = 0;
      if ( !(unsigned int)IMetricsMaxSizeFormat(*(_QWORD *)(dwInstance + 264), 0, &pafd.cbwfx) )
      {
        cbwfx = pafd.cbwfx;
        if ( !pafd.cbwfx )
          goto LABEL_49;
        if ( pafd.cbwfx <= *(_DWORD *)(dwInstance + 240) )
          cbwfx = *(_DWORD *)(dwInstance + 240);
        pafd.cbwfx = cbwfx;
        v7 = GlobalAlloc(0x42u, cbwfx);
        v8 = (struct tWAVEFORMATEX *)GlobalLock(v7);
        v9 = v8;
        if ( !v8 )
          goto LABEL_49;
        v10 = *(_QWORD *)(dwInstance + 256);
        pwfx = v8;
        pafd.cbStruct = 284;
        pafd.pwfx = v8;
        pafd.fdwSupport = 0;
        v12 = *(const void **)(v10 + 404);
        if ( v12 )
        {
          v13 = pafd.cbwfx;
          if ( *(_DWORD *)(dwInstance + 240) < pafd.cbwfx )
            v13 = *(_DWORD *)(dwInstance + 240);
          memcpy_0(v9, v12, v13);
          pwfx = pafd.pwfx;
        }
        fdwEnum = *(_DWORD *)(*(_QWORD *)(dwInstance + 256) + 400LL);
        if ( (fdwEnum & 0x300000) == 0 )
        {
          fdwEnum |= 0x10000u;
          pwfx->wFormatTag = *(_WORD *)(dwInstance + 200);
        }
        pafd.dwFormatTag = v9->wFormatTag;
        LOBYTE(v5) = acmFormatEnumW(0, &pafd, FormatsCallback, dwInstance, fdwEnum) == 0;
        v15 = GlobalHandle(v9);
        GlobalUnlock(v15);
        v16 = GlobalHandle(v9);
        GlobalFree(v16);
      }
      v17 = *(_QWORD *)(dwInstance + 256);
      if ( (*(_DWORD *)(v17 + 4) & 0x40) != 0 && **(_WORD **)(v17 + 16) == *(_WORD *)(dwInstance + 200) )
      {
        pafd.dwFormatTag = *(_DWORD *)(dwInstance + 200);
        pafd.cbStruct = 284;
        pafd.pwfx = *(LPWAVEFORMATEX *)(v17 + 16);
        v18 = *(_WORD **)(v17 + 16);
        pafd.cbwfx = *v18 == 1 ? 16 : (unsigned __int16)v18[8] + 18;
        pafd.fdwSupport = 0;
        if ( !acmFormatDetailsW(0, &pafd, 1u) )
          FormatsCallback(0, &pafd, dwInstance, pafd.fdwSupport);
      }
      v19 = *(_QWORD *)(dwInstance + 256);
      if ( (*(_DWORD *)(v19 + 400) & 0x300000) != 0 && **(_WORD **)(v19 + 404) == *(_WORD *)(dwInstance + 200) )
      {
        pafd.dwFormatTag = *(_DWORD *)(dwInstance + 200);
        pafd.cbStruct = 284;
        pafd.pwfx = *(LPWAVEFORMATEX *)(v19 + 404);
        v20 = *(_WORD **)(v19 + 404);
        if ( *v20 == 1 )
          pafd.cbwfx = 16;
        else
          pafd.cbwfx = (unsigned __int16)v20[8] + 18;
        pafd.fdwSupport = 0;
        if ( !acmFormatDetailsW(0, &pafd, 1u) )
          FormatsCallback(0, &pafd, dwInstance, pafd.fdwSupport);
      }
    }
    else
    {
      memset_0(&pafd, 0, sizeof(pafd));
      v5 = 0;
      if ( !(unsigned int)IMetricsMaxSizeFilter(*(_QWORD *)(dwInstance + 264), 0, &pafd.cbwfx) )
      {
        v21 = pafd.cbwfx;
        if ( !pafd.cbwfx )
          goto LABEL_49;
        if ( pafd.cbwfx <= *(_DWORD *)(dwInstance + 244) )
          v21 = *(_DWORD *)(dwInstance + 244);
        pafd.cbwfx = v21;
        v22 = GlobalAlloc(0x42u, v21);
        v23 = (struct tWAVEFORMATEX *)GlobalLock(v22);
        v24 = v23;
        if ( v23 )
        {
          v25 = *(_QWORD *)(dwInstance + 256);
          v26 = v23;
          pafd.cbStruct = 284;
          pafd.pwfx = v23;
          pafd.fdwSupport = 0;
          v27 = *(DWORD **)(v25 + 404);
          if ( v27 )
          {
            v28 = *v27;
            if ( *v27 >= pafd.cbwfx )
              v28 = pafd.cbwfx;
            memcpy_0(v23, v27, v28);
            v26 = pafd.pwfx;
          }
          v26->nSamplesPerSec = *(_DWORD *)(dwInstance + 200);
          LOBYTE(v5) = acmFilterEnumW(0, (LPACMFILTERDETAILSW)&pafd, FiltersCallback, dwInstance, 0x10000u) == 0;
          v29 = GlobalHandle(v24);
          GlobalUnlock(v29);
          v30 = GlobalHandle(v24);
          GlobalFree(v30);
        }
      }
      v31 = *(_QWORD *)(dwInstance + 256);
      if ( (*(_DWORD *)(v31 + 4) & 0x40) != 0
        && *(_DWORD *)(*(_QWORD *)(v31 + 16) + 4LL) == *(_DWORD *)(dwInstance + 200) )
      {
        pafd.dwFormatTag = *(_DWORD *)(dwInstance + 200);
        pafd.cbStruct = 284;
        pafd.pwfx = *(LPWAVEFORMATEX *)(v31 + 16);
        pafd.cbwfx = **(_DWORD **)(v31 + 16);
        pafd.fdwSupport = 0;
        if ( !acmFilterDetailsW(0, (LPACMFILTERDETAILSW)&pafd, 1u) )
          FiltersCallback(0, (LPACMFILTERDETAILSW)&pafd, dwInstance, pafd.fdwSupport);
      }
    }
    if ( v5 )
    {
LABEL_46:
      if ( (int)SendMessageW(*(HWND *)(dwInstance + 40), 0x146u, 0, 0) > 0 )
      {
        v5 = 1;
LABEL_50:
        EnableWindow(*(HWND *)(dwInstance + 64), v5);
        EnableWindow(*(HWND *)(dwInstance + 88), v5);
        SendMessageW(*(HWND *)(dwInstance + 40), 0xBu, 1u, 0);
        return SetCursor(v4);
      }
      goto LABEL_48;
    }
LABEL_49:
    LoadStringW(
      *(HINSTANCE *)(*(_QWORD *)(dwInstance + 264) + 88LL),
      0x96u,
      (LPWSTR)(*(_QWORD *)(dwInstance + 120) + 2LL),
      ((unsigned __int64)**(unsigned __int16 **)(dwInstance + 120) - 2) >> 1);
    v32 = SendMessageW(*(HWND *)(dwInstance + 40), 0x14Au, 0, *(_QWORD *)(dwInstance + 120) + 2LL);
    SendMessageW(*(HWND *)(dwInstance + 40), 0x151u, v32, 0);
    goto LABEL_50;
  }
  return result;
}

```

## disassembly

```asm
0x180010548  mov     [rsp-8+arg_8], rbx
0x18001054d  mov     [rsp-8+arg_10], rsi
0x180010552  push    rbp
0x180010553  push    rdi
0x180010554  push    r13
0x180010556  push    r14
0x180010558  push    r15
0x18001055a  lea     rbp, [rsp-60h]
0x18001055f  sub     rsp, 160h
0x180010566  mov     rax, cs:__security_cookie
0x18001056d  xor     rax, rsp
0x180010570  mov     [rbp+80h+var_30], rax
0x180010574  mov     rbx, rcx
0x180010577  call    IsSendMessageWPresent
0x18001057c  test    al, al
0x18001057e  jz      loc_180010A4B
0x180010584  mov     edx, 7F02h; lpCursorName
0x180010589  xor     ecx, ecx; hInstance
0x18001058b  call    cs:__imp_LoadCursorW
0x180010591  mov     rcx, rax; hCursor
0x180010594  call    cs:__imp_SetCursor
0x18001059a  mov     rcx, [rbx+28h]; hWnd
0x18001059e  xor     r9d, r9d; lParam
0x1800105a1  xor     r8d, r8d; wParam
0x1800105a4  mov     r15, rax
0x1800105a7  lea     edx, [r9+0Bh]; Msg
0x1800105ab  call    cs:__imp_SendMessageW
0x1800105b1  mov     rcx, rbx
0x1800105b4  call    EmptyFormats
0x1800105b9  mov     rcx, [rbx+28h]; hWnd
0x1800105bd  xor     r9d, r9d; lParam
0x1800105c0  xor     r8d, r8d; wParam
0x1800105c3  mov     edx, 14Bh; Msg
0x1800105c8  call    cs:__imp_SendMessageW
0x1800105ce  cmp     dword ptr [rbx+0C8h], 0
0x1800105d5  mov     r13d, 1
0x1800105db  jz      loc_1800109BC
0x1800105e1  mov     ecx, [rbx]
0x1800105e3  test    ecx, ecx
0x1800105e5  jz      loc_180010837
0x1800105eb  cmp     ecx, r13d
0x1800105ee  jnz     loc_18001099E
0x1800105f4  mov     esi, 11Ch
0x1800105f9  lea     rcx, [rsp+180h+pafd]; void *
0x1800105fe  mov     r8d, esi; Size
0x180010601  xor     edx, edx; Val
0x180010603  call    memset_0
0x180010608  mov     rcx, [rbx+108h]
0x18001060f  lea     r8, [rsp+180h+pafd.cbwfx]
0x180010614  xor     edx, edx
0x180010616  xor     edi, edi
0x180010618  call    IMetricsMaxSizeFormat
0x18001061d  test    eax, eax
0x18001061f  jnz     loc_180010712
0x180010625  mov     ecx, [rsp+180h+pafd.cbwfx]
0x180010629  test    ecx, ecx
0x18001062b  jz      loc_1800109BE
0x180010631  mov     eax, [rbx+0F0h]
0x180010637  cmp     ecx, eax
0x180010639  cmovbe  ecx, eax
0x18001063c  mov     [rsp+180h+pafd.cbwfx], ecx
0x180010640  mov     edx, ecx; dwBytes
0x180010642  lea     ecx, [rdi+42h]; uFlags
0x180010645  call    cs:__imp_GlobalAlloc
0x18001064b  mov     rcx, rax; hMem
0x18001064e  call    cs:__imp_GlobalLock
0x180010654  mov     r14, rax
0x180010657  test    rax, rax
0x18001065a  jz      loc_1800109BE
0x180010660  mov     rcx, [rbx+100h]
0x180010667  mov     r8, rax
0x18001066a  mov     [rsp+180h+pafd.cbStruct], esi
0x18001066e  mov     [rsp+180h+pafd.pwfx], rax
0x180010673  mov     [rsp+180h+pafd.fdwSupport], edi
0x180010677  mov     rdx, [rcx+194h]; Src
0x18001067e  test    rdx, rdx
0x180010681  jz      short loc_1800106A2
0x180010683  mov     ecx, [rbx+0F0h]
0x180010689  mov     eax, [rsp+180h+pafd.cbwfx]
0x18001068d  cmp     ecx, eax
0x18001068f  cmovb   eax, ecx
0x180010692  mov     rcx, r14; void *
0x180010695  mov     r8d, eax; Size
0x180010698  call    memcpy_0
0x18001069d  mov     r8, [rsp+180h+pafd.pwfx]
0x1800106a2  mov     rax, [rbx+100h]
0x1800106a9  mov     ecx, [rax+190h]
0x1800106af  test    ecx, 300000h
0x1800106b5  jnz     short loc_1800106C6
0x1800106b7  movzx   eax, word ptr [rbx+0C8h]
0x1800106be  bts     ecx, 10h
0x1800106c2  mov     [r8], ax
0x1800106c6  movzx   eax, word ptr [r14]
0x1800106ca  lea     r8, FormatsCallback; fnCallback
0x1800106d1  mov     [rsp+180h+fdwEnum], ecx; fdwEnum
0x1800106d5  lea     rdx, [rsp+180h+pafd]; pafd
0x1800106da  xor     ecx, ecx; had
0x1800106dc  mov     [rsp+180h+pafd.dwFormatTag], eax
0x1800106e0  mov     r9, rbx; dwInstance
0x1800106e3  call    acmFormatEnumW
0x1800106e8  test    eax, eax
0x1800106ea  mov     rcx, r14; pMem
0x1800106ed  setz    dil
0x1800106f1  call    cs:__imp_GlobalHandle
0x1800106f7  mov     rcx, rax; hMem
0x1800106fa  call    cs:__imp_GlobalUnlock
0x180010700  mov     rcx, r14; pMem
0x180010703  call    cs:__imp_GlobalHandle
0x180010709  mov     rcx, rax; hMem
0x18001070c  call    cs:__imp_GlobalFree
0x180010712  mov     rdx, [rbx+100h]
0x180010719  mov     r14d, 10h
0x18001071f  mov     eax, [rdx+4]
0x180010722  test    al, 40h
0x180010724  jz      short loc_180010798
0x180010726  mov     rcx, [rdx+10h]
0x18001072a  movzx   eax, word ptr [rbx+0C8h]
0x180010731  cmp     [rcx], ax
0x180010734  jnz     short loc_180010798
0x180010736  mov     eax, [rbx+0C8h]
0x18001073c  mov     [rsp+180h+pafd.dwFormatTag], eax
0x180010740  mov     [rsp+180h+pafd.cbStruct], esi
0x180010744  mov     rax, [rdx+10h]
0x180010748  mov     [rsp+180h+pafd.pwfx], rax
0x18001074d  mov     rax, [rdx+10h]
0x180010751  cmp     r13w, [rax]
0x180010755  jnz     short loc_18001075E
0x180010757  mov     [rsp+180h+pafd.cbwfx], r14d
0x18001075c  jmp     short loc_180010769
0x18001075e  movzx   eax, word ptr [rax+10h]
0x180010762  add     eax, 12h
0x180010765  mov     [rsp+180h+pafd.cbwfx], eax
0x180010769  mov     r8d, r13d; fdwDetails
0x18001076c  mov     [rsp+180h+pafd.fdwSupport], 0
0x180010774  lea     rdx, [rsp+180h+pafd]; pafd
0x180010779  xor     ecx, ecx; had
0x18001077b  call    acmFormatDetailsW
0x180010780  test    eax, eax
0x180010782  jnz     short loc_180010798
0x180010784  mov     r9d, [rsp+180h+pafd.fdwSupport]; fdwSupport
0x180010789  lea     rdx, [rsp+180h+pafd]; pafd
0x18001078e  mov     r8, rbx; dwInstance
0x180010791  xor     ecx, ecx; hadid
0x180010793  call    FormatsCallback
0x180010798  mov     rdx, [rbx+100h]
0x18001079f  test    dword ptr [rdx+190h], 300000h
0x1800107a9  jz      loc_18001099A
0x1800107af  mov     rcx, [rdx+194h]
0x1800107b6  movzx   eax, word ptr [rbx+0C8h]
0x1800107bd  cmp     [rcx], ax
0x1800107c0  jnz     loc_18001099A
0x1800107c6  mov     eax, [rbx+0C8h]
0x1800107cc  mov     [rsp+180h+pafd.dwFormatTag], eax
0x1800107d0  mov     [rsp+180h+pafd.cbStruct], esi
0x1800107d4  mov     rax, [rdx+194h]
0x1800107db  mov     [rsp+180h+pafd.pwfx], rax
0x1800107e0  mov     rax, [rdx+194h]
0x1800107e7  cmp     r13w, [rax]
0x1800107eb  jnz     short loc_1800107F4
0x1800107ed  mov     [rsp+180h+pafd.cbwfx], r14d
0x1800107f2  jmp     short loc_1800107FF
0x1800107f4  movzx   eax, word ptr [rax+10h]
0x1800107f8  add     eax, 12h
0x1800107fb  mov     [rsp+180h+pafd.cbwfx], eax
0x1800107ff  mov     r8d, r13d; fdwDetails
0x180010802  mov     [rsp+180h+pafd.fdwSupport], 0
0x18001080a  lea     rdx, [rsp+180h+pafd]; pafd
0x18001080f  xor     ecx, ecx; had
0x180010811  call    acmFormatDetailsW
0x180010816  test    eax, eax
0x180010818  jnz     loc_18001099A
0x18001081e  mov     r9d, [rsp+180h+pafd.fdwSupport]; fdwSupport
0x180010823  lea     rdx, [rsp+180h+pafd]; pafd
0x180010828  mov     r8, rbx; dwInstance
0x18001082b  xor     ecx, ecx; hadid
0x18001082d  call    FormatsCallback
0x180010832  jmp     loc_18001099A
0x180010837  mov     esi, 11Ch
0x18001083c  lea     rcx, [rsp+180h+pafd]; void *
0x180010841  mov     r8d, esi; Size
0x180010844  xor     edx, edx; Val
0x180010846  call    memset_0
0x18001084b  mov     rcx, [rbx+108h]
0x180010852  lea     r8, [rsp+180h+pafd.cbwfx]
0x180010857  xor     edx, edx
0x180010859  xor     edi, edi
0x18001085b  call    IMetricsMaxSizeFilter
0x180010860  test    eax, eax
0x180010862  jnz     loc_180010933
0x180010868  mov     ecx, [rsp+180h+pafd.cbwfx]
0x18001086c  test    ecx, ecx
0x18001086e  jz      loc_1800109BE
0x180010874  mov     eax, [rbx+0F4h]
0x18001087a  cmp     ecx, eax
0x18001087c  cmovbe  ecx, eax
0x18001087f  mov     [rsp+180h+pafd.cbwfx], ecx
0x180010883  mov     edx, ecx; dwBytes
0x180010885  lea     ecx, [rdi+42h]; uFlags
0x180010888  call    cs:__imp_GlobalAlloc
0x18001088e  mov     rcx, rax; hMem
0x180010891  call    cs:__imp_GlobalLock
0x180010897  mov     r14, rax
0x18001089a  test    rax, rax
0x18001089d  jz      loc_180010933
0x1800108a3  mov     rcx, [rbx+100h]
0x1800108aa  mov     r8, rax
0x1800108ad  mov     [rsp+180h+pafd.cbStruct], esi
0x1800108b1  mov     [rsp+180h+pafd.pwfx], rax
0x1800108b6  mov     [rsp+180h+pafd.fdwSupport], edi
0x1800108ba  mov     rdx, [rcx+194h]; Src
0x1800108c1  test    rdx, rdx
0x1800108c4  jz      short loc_1800108E1
0x1800108c6  mov     ecx, [rdx]
0x1800108c8  cmp     ecx, [rsp+180h+pafd.cbwfx]
0x1800108cc  cmovnb  ecx, [rsp+180h+pafd.cbwfx]
0x1800108d1  mov     r8d, ecx; Size
0x1800108d4  mov     rcx, rax; void *
0x1800108d7  call    memcpy_0
0x1800108dc  mov     r8, [rsp+180h+pafd.pwfx]
0x1800108e1  mov     eax, [rbx+0C8h]
0x1800108e7  lea     rdx, [rsp+180h+pafd]; pafd
0x1800108ec  mov     [r8+4], eax
0x1800108f0  mov     r9, rbx; dwInstance
0x1800108f3  lea     r8, FiltersCallback; fnCallback
0x1800108fa  mov     [rsp+180h+fdwEnum], 10000h; fdwEnum
0x180010902  xor     ecx, ecx; had
0x180010904  call    acmFilterEnumW
0x180010909  test    eax, eax
0x18001090b  mov     rcx, r14; pMem
0x18001090e  setz    dil
0x180010912  call    cs:__imp_GlobalHandle
0x180010918  mov     rcx, rax; hMem
0x18001091b  call    cs:__imp_GlobalUnlock
0x180010921  mov     rcx, r14; pMem
0x180010924  call    cs:__imp_GlobalHandle
0x18001092a  mov     rcx, rax; hMem
0x18001092d  call    cs:__imp_GlobalFree
0x180010933  mov     rcx, [rbx+100h]
0x18001093a  mov     eax, [rcx+4]
0x18001093d  test    al, 40h
0x18001093f  jz      short loc_18001099A
0x180010941  mov     rax, [rcx+10h]
0x180010945  mov     edx, [rbx+0C8h]
0x18001094b  cmp     [rax+4], edx
0x18001094e  jnz     short loc_18001099A
0x180010950  mov     [rsp+180h+pafd.dwFormatTag], edx
0x180010954  mov     r8d, r13d; fdwDetails
0x180010957  mov     [rsp+180h+pafd.cbStruct], esi
0x18001095b  lea     rdx, [rsp+180h+pafd]; pafd
0x180010960  mov     rax, [rcx+10h]
0x180010964  mov     [rsp+180h+pafd.pwfx], rax
0x180010969  mov     rax, [rcx+10h]
0x18001096d  mov     ecx, [rax]
0x18001096f  mov     [rsp+180h+pafd.cbwfx], ecx
0x180010973  xor     ecx, ecx; had
0x180010975  mov     [rsp+180h+pafd.fdwSupport], 0
0x18001097d  call    acmFilterDetailsW
0x180010982  test    eax, eax
0x180010984  jnz     short loc_18001099A
0x180010986  mov     r9d, [rsp+180h+pafd.fdwSupport]; fdwSupport
0x18001098b  lea     rdx, [rsp+180h+pafd]; pafd
0x180010990  mov     r8, rbx; dwInstance
0x180010993  xor     ecx, ecx; hadid
0x180010995  call    FiltersCallback
0x18001099a  test    edi, edi
0x18001099c  jz      short loc_1800109BE
0x18001099e  mov     rcx, [rbx+28h]; hWnd
0x1800109a2  xor     r9d, r9d; lParam
0x1800109a5  xor     r8d, r8d; wParam
0x1800109a8  mov     edx, 146h; Msg
0x1800109ad  call    cs:__imp_SendMessageW
0x1800109b3  test    eax, eax
0x1800109b5  jle     short loc_1800109BC
0x1800109b7  mov     edi, r13d
0x1800109ba  jmp     short loc_180010A16
0x1800109bc  xor     edi, edi
0x1800109be  mov     r8, [rbx+78h]
0x1800109c2  mov     edx, 96h; uID
0x1800109c7  mov     rcx, [rbx+108h]
0x1800109ce  movzx   r9d, word ptr [r8]
0x1800109d2  add     r8, 2; lpBuffer
0x1800109d6  mov     rcx, [rcx+58h]; hInstance
0x1800109da  sub     r9, 2
0x1800109de  shr     r9, 1; cchBufferMax
0x1800109e1  call    cs:__imp_LoadStringW
0x1800109e7  mov     r9, [rbx+78h]
0x1800109eb  xor     r8d, r8d; wParam
0x1800109ee  mov     rcx, [rbx+28h]; hWnd
0x1800109f2  add     r9, 2; lParam
0x1800109f6  mov     edx, 14Ah; Msg
0x1800109fb  call    cs:__imp_SendMessageW
0x180010a01  mov     rcx, [rbx+28h]; hWnd
0x180010a05  xor     r9d, r9d; lParam
0x180010a08  movsxd  r8, eax; wParam
0x180010a0b  mov     edx, 151h; Msg
0x180010a10  call    cs:__imp_SendMessageW
0x180010a16  mov     rcx, [rbx+40h]; hWnd
0x180010a1a  mov     edx, edi; bEnable
0x180010a1c  call    cs:__imp_EnableWindow
0x180010a22  mov     rcx, [rbx+58h]; hWnd
  ... truncated ...
```
