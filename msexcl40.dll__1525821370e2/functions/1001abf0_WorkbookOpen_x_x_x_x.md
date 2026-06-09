# WorkbookOpen(x,x,x,x)

- ea: `0x1001abf0`
- end: `0x1001b1cc`
- name: `_WorkbookOpen@16`
- size: `1500`
- prototype: `int __thiscall(LPCWSTR lpFileName, int, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x10026c60`

## callees

- `0x10011730`
- `0x10012270`
- `0x10018cd0`
- `0x1001ab60`
- `0x1001abf0`
- `0x1001b2f0`
- `0x1001c2b0`
- `0x1001eca0`
- `0x1001f3d0`
- `0x1002580a`
- `0x10025ab7`
- `0x1002ee43`
- `0x10035510`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1001b01a`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1001b01a`

## pseudocode

```c
int __thiscall WorkbookOpen(LPCWSTR lpFileName, int a2, int *a3)
{
  const WCHAR *v3; // esi
  _DWORD *v4; // eax
  int v5; // ecx
  int v6; // eax
  int v7; // esi
  int v8; // ebx
  int v9; // eax
  int v10; // esi
  int *v11; // ecx
  int v12; // edi
  int v13; // ecx
  int v14; // ecx
  __int16 v15; // dx
  int v16; // eax
  int v17; // esi
  bool v18; // cc
  int v19; // eax
  _DWORD *v20; // esi
  int v21; // ebx
  _DWORD *v22; // eax
  _WORD *v23; // esi
  int v24; // ecx
  int v25; // edi
  const wchar_t *v26; // edx
  const wchar_t *v27; // edx
  int v28; // ecx
  const wchar_t *v29; // edx
  const wchar_t *v30; // edx
  _WORD *v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  const unsigned __int16 *i; // edi
  const unsigned __int16 *v36; // esi
  int v37; // eax
  int v38; // ebx
  int v39; // eax
  int v40; // ecx
  int v41; // esi
  int v42; // eax
  int v43; // edx
  int v44; // eax
  int v45; // ebx
  wchar_t *v47; // esi
  int v48; // ecx
  int v49; // edx
  int v50; // eax
  _WORD *v51; // ecx
  _WORD *v52; // eax
  bool v53; // zf
  int v54; // ecx
  _DWORD *v55; // eax
  int v56; // eax
  int v58; // [esp+18h] [ebp-610h] BYREF
  _DWORD *v59; // [esp+1Ch] [ebp-60Ch]
  wchar_t Ext[256]; // [esp+20h] [ebp-608h] BYREF
  wchar_t Filename[256]; // [esp+220h] [ebp-408h] BYREF
  _BYTE v62[516]; // [esp+420h] [ebp-208h] BYREF

  v3 = lpFileName;
  v58 = 0;
  v4 = (_DWORD *)MemAllocate(92);
  v59 = v4;
  if ( !v4 )
    return -1011;
  *v4 = 0;
  if ( (a2 & 0x200) != 0 )
  {
LABEL_7:
    if ( (a2 & 3) != 0 && (a2 & 0x200) == 0 )
    {
      v9 = OpenBiffFile(v3, a2 & 0xFFFFFFFC, (int)&v58);
      v7 = v9;
      if ( !v9 )
      {
        v8 = (int)v59;
        v59[5] = 1;
        goto LABEL_11;
      }
      if ( v9 != -6 )
      {
        v8 = (int)v59;
        goto LABEL_108;
      }
    }
    v8 = (int)v59;
    v7 = XLOLEWorkbookAttach(v5, v59);
    if ( v7 )
      goto LABEL_108;
    v56 = MemAllocate(2092);
    if ( v56 )
    {
      *(_DWORD *)(v8 + 16) = v56;
      goto LABEL_106;
    }
    *(_DWORD *)(v8 + 16) = 0;
    XLOLEWorkbookDetach(v8);
    return -1011;
  }
  v6 = OpenBiffFile(v3, a2, (int)&v58);
  v7 = v6;
  if ( v6 == -6 )
  {
    v3 = lpFileName;
    goto LABEL_7;
  }
  v8 = (int)v59;
  if ( !v6 )
  {
LABEL_11:
    v10 = v58;
    v11 = (int *)v58;
    *(_DWORD *)(v8 + 8) = v58;
    dword_1003A9BC = v8;
    v12 = ExcelScanFile(v11, dword_100384C0, 0);
    if ( v12 < 0 )
    {
      MemFree(v8);
      ExcelCloseFile(v10, 0);
      v13 = v12;
      return TranslateEXErrorToJETError(v13);
    }
    v14 = *(_DWORD *)(v8 + 8);
    v15 = *(_WORD *)(v8 + 44);
    v16 = *(_DWORD *)(v8 + 36);
    v17 = *(_DWORD *)(v8 + 32);
    v18 = *(_DWORD *)(v14 + 4) < 5;
    *(_DWORD *)(v14 + 24) = v17;
    *(_DWORD *)(v14 + 28) = v16;
    *(_WORD *)(v14 + 32) = v15;
    if ( !v18 )
    {
      v19 = *(_DWORD *)(v14 + 40);
      if ( v19 )
      {
        *(_DWORD *)(v19 + 44) = v17;
        *(_WORD *)(v19 + 48) = v15;
      }
    }
    if ( *(int *)(v8 + 4) >= 5 )
    {
      v20 = v59;
      v21 = 0;
      while ( 1 )
      {
        v22 = (_DWORD *)v20[19];
        if ( v22 )
        {
          while ( v22[1] != v21 )
          {
            v22 = (_DWORD *)*v22;
            if ( !v22 )
              goto LABEL_21;
          }
          goto LABEL_56;
        }
LABEL_21:
        FMTV5FormatString(v62, v14);
        if ( !*(_DWORD *)(dword_1003A9BC + 76) )
          dword_1003A9B0 = 0;
        v58 = MemAllocate(20);
        if ( !v58 )
        {
          WorkbookClose(v20, 0);
          v13 = -2;
          return TranslateEXErrorToJETError(v13);
        }
        if ( *(_DWORD *)(dword_1003A9BC + 4) == 4 )
        {
          if ( dword_1003A9B0 == 22 )
          {
            v23 = v62;
            v24 = 2147483646;
            v25 = 256;
            if ( dword_1003B918 )
            {
              v27 = L"hh:mm am/pm";
              do
              {
                if ( !v24 )
                  break;
                if ( !*v27 )
                  break;
                *v23++ = *v27++;
                --v24;
                --v25;
              }
              while ( v25 );
            }
            else
            {
              v26 = L"h:mm am/pm";
              do
              {
                if ( !v24 )
                  break;
                if ( !*v26 )
                  break;
                *v23++ = *v26++;
                --v24;
                --v25;
              }
              while ( v25 );
            }
LABEL_48:
            v31 = v23 - 1;
            if ( v25 )
              v31 = v23;
            v20 = v59;
            *v31 = 0;
            goto LABEL_51;
          }
          if ( dword_1003A9B0 == 23 )
          {
            v23 = v62;
            v28 = 2147483646;
            v25 = 256;
            if ( dword_1003B918 )
            {
              v30 = L"hh:mm:ss am/pm";
              do
              {
                if ( !v28 )
                  break;
                if ( !*v30 )
                  break;
                *v23++ = *v30++;
                --v28;
                --v25;
              }
              while ( v25 );
            }
            else
            {
              v29 = L"h:mm:ss am/pm";
              do
              {
                if ( !v28 )
                  break;
                if ( !*v29 )
                  break;
                *v23++ = *v29++;
                --v28;
                --v25;
              }
              while ( v25 );
            }
            goto LABEL_48;
          }
        }
LABEL_51:
        v32 = FMTStoreFormat(v58 + 8);
        if ( v32 )
        {
          v38 = 8 * (v32 == -2) - 10;
          WorkbookClose(v20, 0);
          v13 = v38;
          return TranslateEXErrorToJETError(v13);
        }
        v14 = v58;
        v33 = dword_1003A9BC;
        ++dword_1003A9B0;
        *(_DWORD *)(v58 + 4) = v21;
        if ( *(_DWORD *)(v33 + 76) )
          *(_DWORD *)dword_1003A9B4 = v14;
        else
          *(_DWORD *)(v33 + 76) = v14;
        dword_1003A9B4 = v14;
LABEL_56:
        if ( ++v21 > 58 )
        {
          v8 = (int)v59;
          break;
        }
      }
    }
    v34 = *(_DWORD *)(v8 + 4);
    if ( v34 == 3 || v34 == 4 )
    {
      __wsplitpath_s(lpFileName, 0, 0, 0, 0, Filename, 0xFFu, Ext, 0xFFu);
      v44 = MemAllocate(528);
      v45 = v44;
      if ( !v44 )
      {
        WorkbookClose(v59, 0);
        return -1011;
      }
      v47 = Filename;
      v48 = dword_1003A9CC;
      v49 = 256;
      *(_DWORD *)(v44 + 4) = dword_1003A9C8;
      v50 = 2147483646;
      *(_DWORD *)(v45 + 8) = v48;
      v51 = (_WORD *)(v45 + 14);
      *(_BYTE *)(v45 + 12) = 1;
      do
      {
        if ( !v50 )
          break;
        if ( !*v47 )
          break;
        *v51++ = *v47++;
        --v50;
        --v49;
      }
      while ( v49 );
      v52 = v51 - 1;
      if ( v49 )
        v52 = v51;
      *v52 = 0;
      v42 = (int)v59;
      v59[20] = v45;
      v8 = v42;
      v53 = *(_DWORD *)(v42 + 4) == 3;
      *(_DWORD *)(v42 + 60) = -1;
      if ( v53 )
      {
        v41 = 14;
        v43 = 7;
      }
      else
      {
        v41 = 18;
        v43 = 11;
      }
    }
    else
    {
      for ( i = *(const unsigned __int16 **)(v8 + 80); i; i = *(const unsigned __int16 **)i )
      {
        if ( *((_BYTE *)i + 12) == 1 )
        {
          v36 = *(const unsigned __int16 **)(*(_DWORD *)(v8 + 8) + 64);
          if ( !v36 )
          {
LABEL_71:
            WorkbookClose(v8, 0);
            v13 = -22;
            return TranslateEXErrorToJETError(v13);
          }
          while ( 1 )
          {
            v37 = wcscmp(v36 + 28, i + 7);
            if ( v37 )
              v37 = v37 < 0 ? -1 : 1;
            if ( !v37 )
              break;
            v36 = *(const unsigned __int16 **)v36;
            if ( !v36 )
            {
              v8 = (int)v59;
              goto LABEL_71;
            }
          }
          v39 = *((_DWORD *)v36 + 6);
          v40 = *((_DWORD *)v36 + 7);
          *((_DWORD *)i + 1) = v39;
          *((_DWORD *)i + 2) = v40;
          if ( (_WORD)v39 || (_WORD)v40 || i[3] )
          {
            v8 = (int)v59;
          }
          else
          {
            v8 = (int)v59;
            if ( !i[5] )
              *((_BYTE *)i + 12) = 0;
          }
        }
      }
      v41 = 14;
      v42 = v8;
      v43 = 7;
    }
    *(_DWORD *)(v8 + 64) = -1;
    *(_DWORD *)(v8 + 68) = -1;
    *(_DWORD *)(v42 + 60) = -1;
    v54 = 0;
    v55 = *(_DWORD **)(v8 + 72);
    if ( v55 )
    {
      do
      {
        if ( !v55[1] )
        {
          if ( v55[2] == v41 )
            *(_DWORD *)(v8 + 64) = v54;
          if ( !v55[1] && v55[2] == v43 )
            *(_DWORD *)(v8 + 68) = v54;
        }
        v55 = (_DWORD *)*v55;
        ++v54;
      }
      while ( v55 );
      *a3 = v8;
      return 0;
    }
LABEL_106:
    *a3 = v8;
    return 0;
  }
LABEL_108:
  MemFree(v8);
  v13 = v7;
  return TranslateEXErrorToJETError(v13);
}

```

## disassembly

```asm
0x1001abf0  mov     edi, edi
0x1001abf2  push    ebp
0x1001abf3  mov     ebp, esp
0x1001abf5  sub     esp, 61Ch
0x1001abfb  mov     eax, ___security_cookie
0x1001ac00  xor     eax, ebp
0x1001ac02  mov     [ebp+var_4], eax
0x1001ac05  mov     eax, [ebp+arg_4]
0x1001ac08  push    ebx
0x1001ac09  push    esi
0x1001ac0a  mov     esi, ecx
0x1001ac0c  mov     [ebp+var_618], eax
0x1001ac12  push    edi
0x1001ac13  mov     ecx, 5Ch ; '\'
0x1001ac18  mov     [ebp+FullPath], esi
0x1001ac1e  mov     [ebp+var_610], 0
0x1001ac28  call    _MemAllocate@4; MemAllocate(x)
0x1001ac2d  mov     [ebp+var_60C], eax
0x1001ac33  test    eax, eax
0x1001ac35  jz      loc_1001B16D
0x1001ac3b  mov     ebx, [ebp+arg_0]
0x1001ac3e  mov     edi, ebx
0x1001ac40  mov     dword ptr [eax], 0
0x1001ac46  and     edi, 200h
0x1001ac4c  jnz     short loc_1001AC79
0x1001ac4e  lea     eax, [ebp+var_610]
0x1001ac54  mov     ecx, esi; lpFileName
0x1001ac56  push    eax; int
0x1001ac57  push    ebx; int
0x1001ac58  call    OpenBiffFile
0x1001ac5d  mov     esi, eax
0x1001ac5f  cmp     esi, 0FFFFFFFAh
0x1001ac62  jz      short loc_1001AC73
0x1001ac64  mov     ebx, [ebp+var_60C]
0x1001ac6a  test    esi, esi
0x1001ac6c  jz      short loc_1001ACB3
0x1001ac6e  jmp     loc_1001B1AB
0x1001ac73  mov     esi, [ebp+FullPath]
0x1001ac79  test    bl, 3
0x1001ac7c  jz      loc_1001B13C
0x1001ac82  test    edi, edi
0x1001ac84  jnz     loc_1001B13C
0x1001ac8a  lea     eax, [ebp+var_610]
0x1001ac90  and     ebx, 0FFFFFFFCh
0x1001ac93  push    eax; int
0x1001ac94  push    ebx; int
0x1001ac95  mov     ecx, esi; lpFileName
0x1001ac97  call    OpenBiffFile
0x1001ac9c  mov     esi, eax
0x1001ac9e  test    esi, esi
0x1001aca0  jnz     loc_1001B137
0x1001aca6  mov     ebx, [ebp+var_60C]
0x1001acac  mov     dword ptr [ebx+14h], 1
0x1001acb3  mov     esi, [ebp+var_610]
0x1001acb9  mov     edx, offset dword_100384C0
0x1001acbe  push    0
0x1001acc0  mov     ecx, esi
0x1001acc2  mov     [ebx+8], esi
0x1001acc5  mov     dword_1003A9BC, ebx
0x1001accb  call    _ExcelScanFile@12; ExcelScanFile(x,x,x)
0x1001acd0  mov     edi, eax
0x1001acd2  test    edi, edi
0x1001acd4  jns     short loc_1001ACED
0x1001acd6  mov     ecx, ebx
0x1001acd8  call    _MemFree@4; MemFree(x)
0x1001acdd  xor     edx, edx
0x1001acdf  mov     ecx, esi
0x1001ace1  call    _ExcelCloseFile@8; ExcelCloseFile(x,x)
0x1001ace6  mov     ecx, edi
0x1001ace8  jmp     loc_1001B1B4
0x1001aced  mov     ecx, [ebx+8]
0x1001acf0  movzx   edx, word ptr [ebx+2Ch]
0x1001acf4  mov     eax, [ebx+24h]
0x1001acf7  mov     esi, [ebx+20h]
0x1001acfa  cmp     dword ptr [ecx+4], 5
0x1001acfe  mov     [ecx+18h], esi
0x1001ad01  mov     [ecx+1Ch], eax
0x1001ad04  mov     [ecx+20h], dx
0x1001ad08  jl      short loc_1001AD18
0x1001ad0a  mov     eax, [ecx+28h]
0x1001ad0d  test    eax, eax
0x1001ad0f  jz      short loc_1001AD18
0x1001ad11  mov     [eax+2Ch], esi
0x1001ad14  mov     [eax+30h], dx
0x1001ad18  cmp     dword ptr [ebx+4], 5
0x1001ad1c  jl      loc_1001AEDE
0x1001ad22  mov     esi, [ebp+var_60C]
0x1001ad28  xor     ebx, ebx
0x1001ad2a  nop     word ptr [eax+eax+00h]
0x1001ad30  mov     eax, [esi+4Ch]
0x1001ad33  test    eax, eax
0x1001ad35  jz      short loc_1001AD46
0x1001ad37  cmp     [eax+4], ebx
0x1001ad3a  jz      loc_1001AECE
0x1001ad40  mov     eax, [eax]
0x1001ad42  test    eax, eax
0x1001ad44  jnz     short loc_1001AD37
0x1001ad46  push    ecx
0x1001ad47  lea     eax, [ebp+var_208]
0x1001ad4d  mov     ecx, ebx
0x1001ad4f  push    eax
0x1001ad50  call    _FMTV5FormatString@16; FMTV5FormatString(x,x,x,x)
0x1001ad55  mov     eax, dword_1003A9BC
0x1001ad5a  cmp     dword ptr [eax+4Ch], 0
0x1001ad5e  jnz     short loc_1001AD6A
0x1001ad60  mov     dword_1003A9B0, 0
0x1001ad6a  mov     ecx, 14h
0x1001ad6f  call    _MemAllocate@4; MemAllocate(x)
0x1001ad74  mov     ecx, eax
0x1001ad76  mov     [ebp+var_610], ecx
0x1001ad7c  test    ecx, ecx
0x1001ad7e  jz      loc_1001AF6B
0x1001ad84  mov     ecx, dword_1003A9BC
0x1001ad8a  cmp     dword ptr [ecx+4], 4
0x1001ad8e  jnz     loc_1001AE80
0x1001ad94  mov     ecx, dword_1003A9B0
0x1001ad9a  cmp     ecx, 16h
0x1001ad9d  jnz     short loc_1001AE0D
0x1001ad9f  cmp     dword_1003B918, 0
0x1001ada6  lea     esi, [ebp+var_208]
0x1001adac  mov     ecx, 7FFFFFFEh
0x1001adb1  mov     edi, 100h
0x1001adb6  jnz     short loc_1001ADE8
0x1001adb8  mov     edx, offset aHMmAmPm_0; "h:mm am/pm"
0x1001adbd  nop     dword ptr [eax]
0x1001adc0  test    ecx, ecx
0x1001adc2  jz      loc_1001AE6D
0x1001adc8  movzx   eax, word ptr [edx]
0x1001adcb  test    ax, ax
0x1001adce  jz      loc_1001AE6D
0x1001add4  mov     [esi], ax
0x1001add7  add     edx, 2
0x1001adda  add     esi, 2
0x1001addd  dec     ecx
0x1001adde  sub     edi, 1
0x1001ade1  jnz     short loc_1001ADC0
0x1001ade3  jmp     loc_1001AE6D
0x1001ade8  mov     edx, offset aHhMmAmPm; "hh:mm am/pm"
0x1001aded  nop     dword ptr [eax]
0x1001adf0  test    ecx, ecx
0x1001adf2  jz      short loc_1001AE6D
0x1001adf4  movzx   eax, word ptr [edx]
0x1001adf7  test    ax, ax
0x1001adfa  jz      short loc_1001AE6D
0x1001adfc  mov     [esi], ax
0x1001adff  add     edx, 2
0x1001ae02  add     esi, 2
0x1001ae05  dec     ecx
0x1001ae06  sub     edi, 1
0x1001ae09  jnz     short loc_1001ADF0
0x1001ae0b  jmp     short loc_1001AE6D
0x1001ae0d  cmp     ecx, 17h
0x1001ae10  jnz     short loc_1001AE80
0x1001ae12  cmp     dword_1003B918, 0
0x1001ae19  lea     esi, [ebp+var_208]
0x1001ae1f  mov     ecx, 7FFFFFFEh
0x1001ae24  mov     edi, 100h
0x1001ae29  jnz     short loc_1001AE4D
0x1001ae2b  mov     edx, offset aHMmSsAmPm; "h:mm:ss am/pm"
0x1001ae30  test    ecx, ecx
0x1001ae32  jz      short loc_1001AE6D
0x1001ae34  movzx   eax, word ptr [edx]
0x1001ae37  test    ax, ax
0x1001ae3a  jz      short loc_1001AE6D
0x1001ae3c  mov     [esi], ax
0x1001ae3f  add     edx, 2
0x1001ae42  add     esi, 2
0x1001ae45  dec     ecx
0x1001ae46  sub     edi, 1
0x1001ae49  jnz     short loc_1001AE30
0x1001ae4b  jmp     short loc_1001AE6D
0x1001ae4d  mov     edx, offset aHhMmSsAmPm; "hh:mm:ss am/pm"
0x1001ae52  test    ecx, ecx
0x1001ae54  jz      short loc_1001AE6D
0x1001ae56  movzx   eax, word ptr [edx]
0x1001ae59  test    ax, ax
0x1001ae5c  jz      short loc_1001AE6D
0x1001ae5e  mov     [esi], ax
0x1001ae61  add     edx, 2
0x1001ae64  add     esi, 2
0x1001ae67  dec     ecx
0x1001ae68  sub     edi, 1
0x1001ae6b  jnz     short loc_1001AE52
0x1001ae6d  test    edi, edi
0x1001ae6f  lea     eax, [esi-2]
0x1001ae72  cmovnz  eax, esi
0x1001ae75  mov     esi, [ebp+var_60C]
0x1001ae7b  xor     ecx, ecx
0x1001ae7d  mov     [eax], cx
0x1001ae80  mov     eax, [ebp+var_610]
0x1001ae86  lea     ecx, [ebp+var_208]
0x1001ae8c  add     eax, 8
0x1001ae8f  mov     edx, offset _ControlPanelSettings
0x1001ae94  push    eax
0x1001ae95  call    _FMTStoreFormat@12; FMTStoreFormat(x,x,x)
0x1001ae9a  test    eax, eax
0x1001ae9c  jnz     loc_1001AF4C
0x1001aea2  mov     ecx, [ebp+var_610]
0x1001aea8  mov     eax, dword_1003A9BC
0x1001aead  inc     dword_1003A9B0
0x1001aeb3  mov     [ecx+4], ebx
0x1001aeb6  cmp     dword ptr [eax+4Ch], 0
0x1001aeba  jnz     short loc_1001AEC1
0x1001aebc  mov     [eax+4Ch], ecx
0x1001aebf  jmp     short loc_1001AEC8
0x1001aec1  mov     eax, dword_1003A9B4
0x1001aec6  mov     [eax], ecx
0x1001aec8  mov     dword_1003A9B4, ecx
0x1001aece  inc     ebx
0x1001aecf  cmp     ebx, 3Ah ; ':'
0x1001aed2  jle     loc_1001AD30
0x1001aed8  mov     ebx, [ebp+var_60C]
0x1001aede  mov     eax, [ebx+4]
0x1001aee1  cmp     eax, 3
0x1001aee4  jz      loc_1001AFF4
0x1001aeea  cmp     eax, 4
0x1001aeed  jz      loc_1001AFF4
0x1001aef3  mov     edi, [ebx+50h]
0x1001aef6  test    edi, edi
0x1001aef8  jz      loc_1001AFE5
0x1001aefe  mov     edi, edi
0x1001af00  cmp     byte ptr [edi+0Ch], 1
0x1001af04  jnz     loc_1001AFDB
0x1001af0a  mov     eax, [ebx+8]
0x1001af0d  mov     esi, [eax+40h]
0x1001af10  test    esi, esi
0x1001af12  jz      loc_1001AF95
0x1001af18  nop     dword ptr [eax+eax+00000000h]
0x1001af20  lea     eax, [edi+0Eh]
0x1001af23  lea     ecx, [esi+38h]
0x1001af26  mov     dx, [ecx]
0x1001af29  cmp     dx, [eax]
0x1001af2c  jnz     short loc_1001AF80
0x1001af2e  test    dx, dx
0x1001af31  jz      short loc_1001AF48
0x1001af33  mov     dx, [ecx+2]
0x1001af37  cmp     dx, [eax+2]
0x1001af3b  jnz     short loc_1001AF80
0x1001af3d  add     ecx, 4
0x1001af40  add     eax, 4
0x1001af43  test    dx, dx
0x1001af46  jnz     short loc_1001AF26
0x1001af48  xor     eax, eax
0x1001af4a  jmp     short loc_1001AF85
0x1001af4c  xor     ebx, ebx
0x1001af4e  mov     ecx, esi
0x1001af50  cmp     eax, 0FFFFFFFEh
0x1001af53  setz    bl
0x1001af56  xor     edx, edx
0x1001af58  lea     ebx, ds:0FFFFFFF6h[ebx*8]
0x1001af5f  call    _WorkbookClose@8; WorkbookClose(x,x)
0x1001af64  mov     ecx, ebx
0x1001af66  jmp     loc_1001B1B4
0x1001af6b  xor     edx, edx
0x1001af6d  mov     ecx, esi
0x1001af6f  mov     ebx, 0FFFFFFFEh
0x1001af74  call    _WorkbookClose@8; WorkbookClose(x,x)
0x1001af79  mov     ecx, ebx
0x1001af7b  jmp     loc_1001B1B4
0x1001af80  sbb     eax, eax
0x1001af82  or      eax, 1
0x1001af85  test    eax, eax
0x1001af87  jz      short loc_1001AFA8
0x1001af89  mov     esi, [esi]
0x1001af8b  test    esi, esi
0x1001af8d  jnz     short loc_1001AF20
0x1001af8f  mov     ebx, [ebp+var_60C]
0x1001af95  xor     edx, edx
0x1001af97  mov     ecx, ebx
0x1001af99  call    _WorkbookClose@8; WorkbookClose(x,x)
0x1001af9e  mov     ecx, 0FFFFFFEAh
0x1001afa3  jmp     loc_1001B1B4
0x1001afa8  mov     eax, [esi+18h]
0x1001afab  mov     ecx, [esi+1Ch]
0x1001afae  mov     [edi+4], eax
0x1001afb1  mov     [edi+8], ecx
0x1001afb4  test    ax, ax
0x1001afb7  jnz     short loc_1001AFD5
0x1001afb9  test    cx, cx
0x1001afbc  jnz     short loc_1001AFD5
0x1001afbe  cmp     [edi+6], cx
0x1001afc2  jnz     short loc_1001AFD5
0x1001afc4  mov     ebx, [ebp+var_60C]
0x1001afca  cmp     [edi+0Ah], cx
0x1001afce  jnz     short loc_1001AFDB
0x1001afd0  mov     [edi+0Ch], cl
0x1001afd3  jmp     short loc_1001AFDB
0x1001afd5  mov     ebx, [ebp+var_60C]
0x1001afdb  mov     edi, [edi]
0x1001afdd  test    edi, edi
0x1001afdf  jnz     loc_1001AF00
0x1001afe5  mov     esi, 0Eh
0x1001afea  mov     eax, ebx
0x1001afec  lea     edx, [esi-7]
0x1001afef  jmp     loc_1001B0D0
0x1001aff4  push    0FFh; ExtCount
0x1001aff9  lea     eax, [ebp+Ext]
0x1001afff  push    eax; Ext
0x1001b000  push    0FFh; FilenameCount
0x1001b005  lea     eax, [ebp+Filename]
  ... truncated ...
```
