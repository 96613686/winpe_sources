# CDataSource::UtilInitialize(int,long &)

- ea: `0x1001a2a0`
- end: `0x1001a527`
- name: `?UtilInitialize@CDataSource@@QAEJHAAJ@Z`
- size: `647`
- prototype: `int __thiscall(LPARAM dwInitParam, int, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1001a540`
- `0x1001a970`

## callees

- `0x10018f30`
- `0x1001a2a0`
- `0x1001c380`
- `0x1001f2d0`

## import_xrefs

- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001a4dc`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001a4dc`
- `USER32!DialogBoxParamA` at `0x1001a485`
- `USER32!DialogBoxParamA` at `0x1001a4b3`
- `USER32!DialogBoxParamA` at `0x1001a485`
- `USER32!DialogBoxParamA` at `0x1001a4b3`
- `msjet40!__imp__JetInit@4` at `0x1001a371`
- `msjet40!__imp__JetInit@4` at `0x1001a371`
- `msjet40!__imp__JetSetSystemParameter@20` at `0x1001a34f`
- `msjet40!__imp__JetSetSystemParameter@20` at `0x1001a3d4`
- `msjet40!__imp__JetSetSystemParameter@20` at `0x1001a34f`
- `msjet40!__imp__JetSetSystemParameter@20` at `0x1001a3d4`
- `msjet40!__imp__JetTerm@4` at `0x1001a50f`
- `msjet40!__imp__JetTerm@4` at `0x1001a50f`

## pseudocode

```c
int __thiscall CDataSource::UtilInitialize(LPARAM dwInitParam, int a2, int *a3)
{
  int v4; // esi
  _WORD *v5; // ebx
  int v6; // eax
  JoltProperties *v7; // ecx
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  JoltProperties *v12; // ebx
  int v13; // eax
  int v14; // eax
  HWND v15; // ebx
  _DWORD *v16; // ebx
  struct _GUID *v18; // [esp+0h] [ebp-20h]
  int v19; // [esp+4h] [ebp-1Ch]
  int v20; // [esp+Ch] [ebp-14h]
  __int16 v21; // [esp+Ch] [ebp-14h]
  unsigned int v22; // [esp+10h] [ebp-10h] BYREF
  unsigned int v23; // [esp+14h] [ebp-Ch] BYREF
  unsigned int v24; // [esp+18h] [ebp-8h]
  int v25; // [esp+1Ch] [ebp-4h]

  v24 = 251;
  v4 = 0;
  v25 = 55;
  v5 = 0;
  if ( *(_DWORD *)(dwInitParam + 128) == 1 )
  {
    v4 = -2147217838;
LABEL_35:
    v16 = (_DWORD *)(dwInitParam + 140);
    CExtError::SendHRtoOLEAuto((int)&IID_IDBInitialize, 0, v18, v19);
    goto LABEL_39;
  }
  if ( !*(_DWORD *)(dwInitParam + 140) )
  {
    LOWORD(v6) = 0;
    v20 = 0;
    do
    {
      v7 = *(JoltProperties **)(dwInitParam + 164);
      v23 = 8 * (unsigned __int16)v6;
      if ( JoltProperties::BinarySearch(v7, *(unsigned int *)((char *)&v24 + v23), &v22) >= 0 )
      {
        v8 = *(_DWORD *)(*(_DWORD *)(dwInitParam + 164) + 16);
        if ( *(_WORD *)(v8 + 48 * v22 + 16) == 8 )
          v5 = *(_WORD **)(v8 + 48 * v22 + 24);
      }
      if ( v5 )
      {
        if ( *v5 )
        {
          v9 = JetSetSystemParameter(dwInitParam + 96, -1, *(int *)((char *)&v25 + v23), 0, v5);
          *a3 = v9;
          if ( v9 < 0 )
            goto LABEL_13;
        }
      }
      v6 = v20 + 1;
      v20 = v6;
    }
    while ( !(_WORD)v6 );
    if ( JetInit((JET_INSTANCE *)(dwInitParam + 96)) )
    {
LABEL_13:
      v4 = -2147467259;
      goto LABEL_35;
    }
    if ( JoltProperties::BinarySearch(*(JoltProperties **)(dwInitParam + 164), 0xFAu, &v23) >= 0 )
    {
      v10 = *(_DWORD *)(*(_DWORD *)(dwInitParam + 164) + 16);
      if ( *(_WORD *)(v10 + 48 * v23 + 16) == 8 )
        v5 = *(_WORD **)(v10 + 48 * v23 + 24);
    }
    if ( v5 )
    {
      if ( *v5 )
      {
        v11 = JetSetSystemParameter(dwInitParam + 96, -1, 0, 0, v5);
        *a3 = v11;
        if ( v11 < 0 )
        {
          v4 = -2147467259;
          goto LABEL_35;
        }
      }
    }
  }
  v12 = *(JoltProperties **)(dwInitParam + 160);
  if ( JoltProperties::BinarySearch(v12, 0x40u, &v23) >= 0
    && (v13 = *((_DWORD *)v12 + 4), *(_WORD *)(v13 + 48 * v23 + 16) == 2) )
  {
    v21 = *(_WORD *)(v13 + 48 * v23 + 24);
  }
  else
  {
    v21 = 0;
  }
  if ( JoltProperties::BinarySearch(v12, 0x3Cu, &v23) >= 0
    && (v14 = *((_DWORD *)v12 + 4), *(_WORD *)(v14 + 48 * v23 + 16) == 3) )
  {
    v15 = *(HWND *)(v14 + 48 * v23 + 24);
  }
  else
  {
    v15 = 0;
  }
  switch ( v21 )
  {
    case 1:
      if ( DialogBoxParamA(g_hinstance, (LPCSTR)0x65, v15, DlgProc, dwInitParam) )
        goto LABEL_34;
      goto LABEL_37;
    case 2:
    case 3:
      v4 = CDataSource::AttemptInitialize((CDataSource *)v18, v19);
      if ( v4 >= 0 )
        return v4;
      if ( DialogBoxParamA(g_hinstance, (LPCSTR)0x65, v15, DlgProc, dwInitParam) )
      {
LABEL_34:
        v4 = -2147217842;
        goto LABEL_35;
      }
      SetErrorInfo(0, 0);
LABEL_37:
      v4 = CDataSource::AttemptInitialize((CDataSource *)v18, v19);
      if ( v4 >= 0 )
        return v4;
      v16 = (_DWORD *)(dwInitParam + 140);
      break;
    case 4:
      goto LABEL_37;
    default:
      return v4;
  }
LABEL_39:
  if ( v4 != -2147217838 && *(_DWORD *)(dwInitParam + 96) )
  {
    if ( !*v16 )
      JetTerm(*(_DWORD *)(dwInitParam + 96));
    *(_DWORD *)(dwInitParam + 96) = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x1001a2a0  mov     edi, edi
0x1001a2a2  push    ebp
0x1001a2a3  mov     ebp, esp
0x1001a2a5  and     esp, 0FFFFFFF8h
0x1001a2a8  sub     esp, 14h
0x1001a2ab  push    ebx
0x1001a2ac  push    esi; int
0x1001a2ad  push    edi; this
0x1001a2ae  mov     edi, ecx
0x1001a2b0  mov     [esp+20h+var_8], 0FBh
0x1001a2b8  xor     esi, esi
0x1001a2ba  mov     [esp+20h+var_4], 37h ; '7'
0x1001a2c2  xor     ebx, ebx
0x1001a2c4  cmp     dword ptr [edi+80h], 1
0x1001a2cb  jnz     short loc_1001A2D7
0x1001a2cd  mov     esi, 80040E52h
0x1001a2d2  jmp     loc_1001A4C2
0x1001a2d7  cmp     [edi+8Ch], ebx
0x1001a2dd  jnz     loc_1001A3ED
0x1001a2e3  xor     eax, eax
0x1001a2e5  mov     [esp+20h+var_14], eax
0x1001a2e9  nop     dword ptr [eax+00000000h]
0x1001a2f0  movzx   eax, ax
0x1001a2f3  lea     ecx, [esp+20h+var_10]
0x1001a2f7  shl     eax, 3
0x1001a2fa  push    ecx; unsigned int *
0x1001a2fb  mov     ecx, [edi+0A4h]; this
0x1001a301  mov     [esp+24h+var_C], eax
0x1001a305  push    [esp+eax+24h+var_8]; unsigned int
0x1001a309  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x1001a30e  test    eax, eax
0x1001a310  js      short loc_1001A334
0x1001a312  mov     eax, [esp+20h+var_10]
0x1001a316  mov     edx, 8
0x1001a31b  lea     ecx, [eax+eax*2]
0x1001a31e  mov     eax, [edi+0A4h]
0x1001a324  add     ecx, ecx
0x1001a326  mov     eax, [eax+10h]
0x1001a329  cmp     dx, [eax+ecx*8+10h]
0x1001a32e  jnz     short loc_1001A334
0x1001a330  mov     ebx, [eax+ecx*8+18h]
0x1001a334  test    ebx, ebx
0x1001a336  jz      short loc_1001A35E
0x1001a338  xor     eax, eax
0x1001a33a  cmp     ax, [ebx]
0x1001a33d  jz      short loc_1001A35E
0x1001a33f  push    ebx
0x1001a340  push    eax
0x1001a341  mov     eax, [esp+28h+var_C]
0x1001a345  push    [esp+eax+28h+var_4]
0x1001a349  lea     eax, [edi+60h]
0x1001a34c  push    0FFFFFFFFh
0x1001a34e  push    eax
0x1001a34f  call    ds:__imp__JetSetSystemParameter@20; JetSetSystemParameter(x,x,x,x,x)
0x1001a355  mov     ecx, [ebp+arg_4]
0x1001a358  mov     [ecx], eax
0x1001a35a  test    eax, eax
0x1001a35c  js      short loc_1001A37B
0x1001a35e  mov     eax, [esp+20h+var_14]
0x1001a362  inc     eax
0x1001a363  mov     [esp+20h+var_14], eax
0x1001a367  cmp     ax, 1
0x1001a36b  jb      short loc_1001A2F0
0x1001a36d  lea     eax, [edi+60h]
0x1001a370  push    eax; pinstance
0x1001a371  call    ds:__imp__JetInit@4; JetInit(x)
0x1001a377  test    eax, eax
0x1001a379  jz      short loc_1001A385
0x1001a37b  mov     esi, 80004005h
0x1001a380  jmp     loc_1001A4C2
0x1001a385  mov     ecx, [edi+0A4h]; this
0x1001a38b  lea     eax, [esp+20h+var_C]
0x1001a38f  push    eax; unsigned int *
0x1001a390  push    0FAh; unsigned int
0x1001a395  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x1001a39a  test    eax, eax
0x1001a39c  js      short loc_1001A3C0
0x1001a39e  mov     eax, [esp+20h+var_C]
0x1001a3a2  mov     edx, 8
0x1001a3a7  lea     ecx, [eax+eax*2]
0x1001a3aa  mov     eax, [edi+0A4h]
0x1001a3b0  add     ecx, ecx
0x1001a3b2  mov     eax, [eax+10h]
0x1001a3b5  cmp     dx, [eax+ecx*8+10h]
0x1001a3ba  jnz     short loc_1001A3C0
0x1001a3bc  mov     ebx, [eax+ecx*8+18h]
0x1001a3c0  test    ebx, ebx
0x1001a3c2  jz      short loc_1001A3ED
0x1001a3c4  xor     eax, eax
0x1001a3c6  cmp     ax, [ebx]
0x1001a3c9  jz      short loc_1001A3ED
0x1001a3cb  push    ebx
0x1001a3cc  push    eax
0x1001a3cd  push    eax
0x1001a3ce  push    0FFFFFFFFh
0x1001a3d0  lea     eax, [edi+60h]
0x1001a3d3  push    eax
0x1001a3d4  call    ds:__imp__JetSetSystemParameter@20; JetSetSystemParameter(x,x,x,x,x)
0x1001a3da  mov     ecx, [ebp+arg_4]
0x1001a3dd  mov     [ecx], eax
0x1001a3df  test    eax, eax
0x1001a3e1  jns     short loc_1001A3ED
0x1001a3e3  mov     esi, 80004005h
0x1001a3e8  jmp     loc_1001A4C2
0x1001a3ed  mov     ebx, [edi+0A0h]
0x1001a3f3  lea     eax, [esp+20h+var_C]
0x1001a3f7  push    eax; unsigned int *
0x1001a3f8  push    40h ; '@'; unsigned int
0x1001a3fa  mov     ecx, ebx; this
0x1001a3fc  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x1001a401  test    eax, eax
0x1001a403  js      short loc_1001A428
0x1001a405  mov     eax, [esp+20h+var_C]
0x1001a409  mov     edx, 2
0x1001a40e  lea     ecx, [eax+eax*2]
0x1001a411  mov     eax, [ebx+10h]
0x1001a414  add     ecx, ecx
0x1001a416  cmp     dx, [eax+ecx*8+10h]
0x1001a41b  jnz     short loc_1001A428
0x1001a41d  movzx   eax, word ptr [eax+ecx*8+18h]
0x1001a422  mov     [esp+20h+var_14], eax
0x1001a426  jmp     short loc_1001A42C
0x1001a428  mov     [esp+20h+var_14], esi
0x1001a42c  lea     eax, [esp+20h+var_C]
0x1001a430  mov     ecx, ebx; this
0x1001a432  push    eax; unsigned int *
0x1001a433  push    3Ch ; '<'; unsigned int
0x1001a435  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x1001a43a  test    eax, eax
0x1001a43c  js      short loc_1001A45C
0x1001a43e  mov     eax, [esp+20h+var_C]
0x1001a442  mov     edx, 3
0x1001a447  lea     ecx, [eax+eax*2]
0x1001a44a  mov     eax, [ebx+10h]
0x1001a44d  add     ecx, ecx
0x1001a44f  cmp     dx, [eax+ecx*8+10h]
0x1001a454  jnz     short loc_1001A45C
0x1001a456  mov     ebx, [eax+ecx*8+18h]
0x1001a45a  jmp     short loc_1001A45E
0x1001a45c  xor     ebx, ebx
0x1001a45e  mov     eax, [esp+20h+var_14]
0x1001a462  movzx   eax, ax
0x1001a465  dec     eax; switch 4 cases
0x1001a466  cmp     eax, 3
0x1001a469  ja      def_1001A46F; jumptable 1001A46F default case
0x1001a46f  jmp     ds:jpt_1001A46F[eax*4]; switch jump
0x1001a476  push    edi; jumptable 1001A46F case 1
0x1001a477  push    offset ?DlgProc@@YGHPAUHWND__@@IIJ@Z; lpDialogFunc
0x1001a47c  push    ebx; hWndParent
0x1001a47d  push    65h ; 'e'; lpTemplateName
0x1001a47f  push    ?g_hinstance@@3PAUHINSTANCE__@@A; hInstance
0x1001a485  call    ds:__imp__DialogBoxParamA@20; DialogBoxParamA(x,x,x,x,x)
0x1001a48b  test    eax, eax
0x1001a48d  jnz     short loc_1001A4BD
0x1001a48f  mov     edx, [ebp+arg_0]
0x1001a492  jmp     short loc_1001A4E7
0x1001a494  mov     edx, [ebp+arg_0]; jumptable 1001A46F cases 2,3
0x1001a497  mov     ecx, edi
0x1001a499  call    ?AttemptInitialize@CDataSource@@QAGJH@Z; CDataSource::AttemptInitialize(int)
0x1001a49e  mov     esi, eax
0x1001a4a0  test    esi, esi
0x1001a4a2  jns     short def_1001A46F; jumptable 1001A46F default case
0x1001a4a4  push    edi; dwInitParam
0x1001a4a5  push    offset ?DlgProc@@YGHPAUHWND__@@IIJ@Z; lpDialogFunc
0x1001a4aa  push    ebx; hWndParent
0x1001a4ab  push    65h ; 'e'; lpTemplateName
0x1001a4ad  push    ?g_hinstance@@3PAUHINSTANCE__@@A; hInstance
0x1001a4b3  call    ds:__imp__DialogBoxParamA@20; DialogBoxParamA(x,x,x,x,x)
0x1001a4b9  test    eax, eax
0x1001a4bb  jz      short loc_1001A4D8
0x1001a4bd  mov     esi, 80040E4Eh
0x1001a4c2  push    0; int
0x1001a4c4  push    offset _IID_IDBInitialize; int
0x1001a4c9  mov     edx, esi
0x1001a4cb  lea     ebx, [edi+8Ch]
0x1001a4d1  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x1001a4d6  jmp     short loc_1001A4FA
0x1001a4d8  push    0; perrinfo
0x1001a4da  push    0; dwReserved
0x1001a4dc  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1001a4e2  mov     eax, [ebp+arg_0]; jumptable 1001A46F case 4
0x1001a4e5  mov     edx, eax
0x1001a4e7  mov     ecx, edi
0x1001a4e9  call    ?AttemptInitialize@CDataSource@@QAGJH@Z; CDataSource::AttemptInitialize(int)
0x1001a4ee  mov     esi, eax
0x1001a4f0  test    esi, esi
0x1001a4f2  jns     short def_1001A46F; jumptable 1001A46F default case
0x1001a4f4  lea     ebx, [edi+8Ch]
0x1001a4fa  cmp     esi, 80040E52h
0x1001a500  jz      short def_1001A46F; jumptable 1001A46F default case
0x1001a502  mov     eax, [edi+60h]
0x1001a505  test    eax, eax
0x1001a507  jz      short def_1001A46F; jumptable 1001A46F default case
0x1001a509  cmp     dword ptr [ebx], 0
0x1001a50c  jnz     short loc_1001A515
0x1001a50e  push    eax; instance
0x1001a50f  call    ds:__imp__JetTerm@4; JetTerm(x)
0x1001a515  mov     dword ptr [edi+60h], 0
0x1001a51c  pop     edi; jumptable 1001A46F default case
0x1001a51d  mov     eax, esi
0x1001a51f  pop     esi
0x1001a520  pop     ebx
0x1001a521  mov     esp, ebp
0x1001a523  pop     ebp
0x1001a524  retn    8
```
