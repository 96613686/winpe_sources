# TextCreateFile(x,x,x,x)

- ea: `0x1001ee70`
- end: `0x1001efb2`
- name: `_TextCreateFile@16`
- size: `322`
- prototype: `int __stdcall(int, STRSAFE_LPCWSTR pszSrc, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x1000ed90`

## callees

- `0x1001ede0`
- `0x1001ee70`
- `0x10020470`
- `0x100215c0`
- `0x10022400`
- `0x10029870`

## pseudocode

```c
int __stdcall TextCreateFile(int a1, STRSAFE_LPCWSTR pszSrc, int a3, LPCWSTR *a4)
{
  int v4; // ebx
  int *v5; // esi
  int result; // eax
  LPCWSTR v7; // ebp
  int ExportFile; // edi
  int i; // edi
  _WORD *v10; // eax
  bool v11; // zf
  LPCWSTR lpFileName; // [esp+10h] [ebp-Ch] BYREF
  int v14; // [esp+14h] [ebp-8h] BYREF
  int v15; // [esp+18h] [ebp-4h] BYREF

  v4 = a3;
  v5 = *(int **)(a3 + 8);
  *a4 = 0;
  a3 = 0;
  v14 = 0;
  result = TextSetup(a1, pszSrc, v4, (STRSAFE_LPWSTR *)&lpFileName);
  v7 = lpFileName;
  ExportFile = result;
  if ( !result )
  {
    ExportFile = TextDetectCodePageInfo(
                   lpFileName,
                   0,
                   v4 + 36,
                   0,
                   0,
                   (int)&v14,
                   (int)&v15,
                   (int)&a1,
                   *(_DWORD *)(v4 + 52));
    if ( ExportFile )
      goto LABEL_16;
    *((_DWORD *)v7 + 135) = 1;
    *((_DWORD *)v7 + 2193) = 1;
    ExportFile = TextCreateExportFile(v7, (int)(v7 + 264), *(_DWORD *)(v4 + 52));
    if ( ExportFile )
      goto LABEL_16;
    if ( *(_DWORD *)(v4 + 52) != 3 && *(_DWORD *)(v4 + 28) )
    {
      for ( i = 5; v5; i = 4 )
      {
        v10 = v5 + 9;
        v11 = *(_WORD *)(v4 + 72) == 0;
        pszSrc = (STRSAFE_LPCWSTR)v5 + 19;
        while ( *v10++ )
          ;
        ExportFile = TextPutNextField((int)v7, v5 + 9, 0, v10 - pszSrc, (int)&a3, i, !v11);
        if ( ExportFile )
          goto LABEL_16;
        v5 = (int *)*v5;
      }
      ExportFile = TextPutNextField((int)v7, 0, 0, 0, (int)&a3, 6, 0);
      if ( ExportFile )
      {
LABEL_16:
        TextFreeResources(v7);
        return ExportFile;
      }
    }
    *a4 = v7;
LABEL_15:
    if ( !ExportFile )
      return ExportFile;
    goto LABEL_16;
  }
  if ( result != -1011 )
    goto LABEL_15;
  return result;
}

```

## disassembly

```asm
0x1001ee70  sub     esp, 0Ch
0x1001ee73  mov     eax, [esp+0Ch+arg_C]
0x1001ee77  push    ebx
0x1001ee78  mov     ebx, [esp+10h+arg_8]
0x1001ee7c  push    ebp
0x1001ee7d  push    esi
0x1001ee7e  push    edi
0x1001ee7f  mov     esi, [ebx+8]
0x1001ee82  mov     dword ptr [eax], 0
0x1001ee88  lea     eax, [esp+1Ch+lpFileName]
0x1001ee8c  push    eax; int
0x1001ee8d  push    ebx; int
0x1001ee8e  push    [esp+24h+pszSrc]; pszSrc
0x1001ee92  mov     [esp+28h+arg_8], 0
0x1001ee9a  push    [esp+28h+arg_0]; int
0x1001ee9e  mov     [esp+2Ch+var_8], 0
0x1001eea6  call    TextSetup
0x1001eeab  mov     ebp, [esp+1Ch+lpFileName]
0x1001eeaf  mov     edi, eax
0x1001eeb1  test    edi, edi
0x1001eeb3  jz      short loc_1001EECB
0x1001eeb5  cmp     edi, 0FFFFFC0Dh
0x1001eebb  jnz     loc_1001EF9C
0x1001eec1  pop     edi
0x1001eec2  pop     esi
0x1001eec3  pop     ebp
0x1001eec4  pop     ebx
0x1001eec5  add     esp, 0Ch
0x1001eec8  retn    10h
0x1001eecb  push    dword ptr [ebx+34h]; int
0x1001eece  lea     eax, [esp+20h+arg_0]
0x1001eed2  push    eax; int
0x1001eed3  lea     eax, [esp+24h+var_4]
0x1001eed7  push    eax; int
0x1001eed8  lea     eax, [esp+28h+var_8]
0x1001eedc  push    eax; int
0x1001eedd  push    0; Locale
0x1001eedf  push    0; int
0x1001eee1  lea     eax, [ebx+24h]
0x1001eee4  push    eax; int
0x1001eee5  push    0; int
0x1001eee7  push    ebp; lpFileName
0x1001eee8  call    _TextDetectCodePageInfo@36; TextDetectCodePageInfo(x,x,x,x,x,x,x,x,x)
0x1001eeed  mov     edi, eax
0x1001eeef  test    edi, edi
0x1001eef1  jnz     loc_1001EFA0
0x1001eef7  lea     eax, [ebp+210h]
0x1001eefd  mov     dword ptr [eax+0Ch], 1
0x1001ef04  mov     dword ptr [eax+2034h], 1
0x1001ef0e  push    dword ptr [ebx+34h]; int
0x1001ef11  push    eax; int
0x1001ef12  push    ebp; lpFileName
0x1001ef13  call    TextCreateExportFile
0x1001ef18  mov     edi, eax
0x1001ef1a  test    edi, edi
0x1001ef1c  jnz     loc_1001EFA0
0x1001ef22  cmp     dword ptr [ebx+34h], 3
0x1001ef26  jz      short loc_1001EF96
0x1001ef28  cmp     [ebx+1Ch], eax
0x1001ef2b  jz      short loc_1001EF96
0x1001ef2d  lea     edi, [eax+5]
0x1001ef30  test    esi, esi
0x1001ef32  jz      short loc_1001EF7B
0x1001ef34  xor     edx, edx
0x1001ef36  lea     eax, [esi+24h]
0x1001ef39  cmp     [ebx+48h], dx
0x1001ef3d  lea     ecx, [eax+2]
0x1001ef40  mov     [esp+1Ch+pszSrc], ecx
0x1001ef44  setnz   dl
0x1001ef47  mov     cx, [eax]
0x1001ef4a  add     eax, 2
0x1001ef4d  test    cx, cx
0x1001ef50  jnz     short loc_1001EF47
0x1001ef52  sub     eax, [esp+1Ch+pszSrc]
0x1001ef56  lea     ecx, [esp+1Ch+arg_8]
0x1001ef5a  push    edx; int
0x1001ef5b  push    edi; int
0x1001ef5c  push    ecx; int
0x1001ef5d  sar     eax, 1
0x1001ef5f  push    eax; int
0x1001ef60  push    0; int
0x1001ef62  lea     eax, [esi+24h]
0x1001ef65  push    eax; Src
0x1001ef66  push    ebp; int
0x1001ef67  call    _TextPutNextField@28; TextPutNextField(x,x,x,x,x,x,x)
0x1001ef6c  mov     edi, eax
0x1001ef6e  test    edi, edi
0x1001ef70  jnz     short loc_1001EFA0
0x1001ef72  mov     esi, [esi]
0x1001ef74  lea     edi, [eax+4]
0x1001ef77  test    esi, esi
0x1001ef79  jnz     short loc_1001EF34
0x1001ef7b  push    0; int
0x1001ef7d  push    6; int
0x1001ef7f  lea     eax, [esp+24h+arg_8]
0x1001ef83  push    eax; int
0x1001ef84  push    0; int
0x1001ef86  push    0; int
0x1001ef88  push    0; Src
0x1001ef8a  push    ebp; int
0x1001ef8b  call    _TextPutNextField@28; TextPutNextField(x,x,x,x,x,x,x)
0x1001ef90  mov     edi, eax
0x1001ef92  test    edi, edi
0x1001ef94  jnz     short loc_1001EFA0
0x1001ef96  mov     eax, [esp+1Ch+arg_C]
0x1001ef9a  mov     [eax], ebp
0x1001ef9c  test    edi, edi
0x1001ef9e  jz      short loc_1001EFA6
0x1001efa0  push    ebp
0x1001efa1  call    _TextFreeResources@4; TextFreeResources(x)
0x1001efa6  mov     eax, edi
0x1001efa8  pop     edi
0x1001efa9  pop     esi
0x1001efaa  pop     ebp
0x1001efab  pop     ebx
0x1001efac  add     esp, 0Ch
0x1001efaf  retn    10h
```
