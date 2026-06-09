# AdvancedPage::RefreshIntentComboBoxDefault(void)

- ea: `0x180010404`
- end: `0x180010777`
- name: `?RefreshIntentComboBoxDefault@AdvancedPage@@AEAAJXZ`
- size: `883`
- prototype: `__int64 __fastcall(HWND **this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180010388`

## callees

- `0x180001334`
- `0x18000134c`
- `0x18000fb18`
- `0x180010404`
- `0x18001772c`
- `0x1800178d4`
- `0x1800179f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800104d0`
- `KERNEL32!GetLastError` at `0x1800106ae`
- `KERNEL32!GetLastError` at `0x1800104d0`
- `KERNEL32!GetLastError` at `0x1800106ae`
- `USER32!SendMessageW` at `0x180010438`
- `USER32!SendMessageW` at `0x180010461`
- `USER32!SendMessageW` at `0x180010490`
- `USER32!SendMessageW` at `0x1800104b2`
- `USER32!SendMessageW` at `0x180010632`
- `USER32!SendMessageW` at `0x1800106e3`
- `USER32!SendMessageW` at `0x18001070c`
- `USER32!SendMessageW` at `0x18001073b`
- `USER32!SendMessageW` at `0x180010438`
- `USER32!SendMessageW` at `0x180010461`
- `USER32!SendMessageW` at `0x180010490`
- `USER32!SendMessageW` at `0x1800104b2`
- `USER32!SendMessageW` at `0x180010632`
- `USER32!SendMessageW` at `0x1800106e3`
- `USER32!SendMessageW` at `0x18001070c`
- `USER32!SendMessageW` at `0x18001073b`
- `mscms!ColorCplGetDefaultRenderingIntentScope` at `0x180010604`
- `mscms!ColorCplGetDefaultRenderingIntentScope` at `0x180010604`
- `mscms!WcsGetDefaultRenderingIntent` at `0x1800104c6`
- `mscms!WcsGetDefaultRenderingIntent` at `0x18001069f`
- `mscms!WcsGetDefaultRenderingIntent` at `0x1800104c6`
- `mscms!WcsGetDefaultRenderingIntent` at `0x18001069f`

## pseudocode

```c
__int64 __fastcall AdvancedPage::RefreshIntentComboBoxDefault(HWND **this)
{
  void *v2; // rsi
  int v3; // eax
  int v4; // edi
  int v5; // ebx
  WPARAM v6; // r15
  _DWORD *v7; // rax
  HWND *v8; // rbx
  void *v9; // rax
  signed int LastError; // eax
  int StringFromRC; // ebx
  int v12; // eax
  __int64 v13; // rdi
  HINSTANCE v14; // rdx
  HINSTANCE v15; // rdx
  UINT v16; // r8d
  _DWORD *v17; // rax
  LPARAM v18; // rdx
  HWND *v19; // rcx
  int v20; // edi
  int v21; // edi
  int v22; // eax
  WCS_PROFILE_MANAGEMENT_SCOPE v23; // ecx
  signed int v24; // edi
  signed int v25; // eax
  int v26; // eax
  int v27; // esi
  int v28; // edi
  _DWORD *v29; // rax
  int v30; // esi
  int v31; // eax
  int v33; // [rsp+20h] [rbp-30h] BYREF
  unsigned __int16 *v34; // [rsp+28h] [rbp-28h]
  int v35; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v36; // [rsp+38h] [rbp-18h]
  int v37; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int16 *v38; // [rsp+48h] [rbp-8h]
  DWORD pdwRenderingIntent; // [rsp+80h] [rbp+30h] BYREF
  DWORD v40; // [rsp+88h] [rbp+38h] BYREF
  int v41; // [rsp+90h] [rbp+40h] BYREF

  if ( *((_DWORD *)this + 8) == 1 )
  {
    v2 = 0;
    v3 = SendMessageW(*this[7], 0x146u, 0, 0);
    v4 = v3;
    if ( v3 != -1 )
    {
      v5 = 0;
      if ( v3 > 0 )
      {
        do
        {
          v6 = v5;
          v7 = (_DWORD *)SendMessageW(*this[7], 0x150u, v5, 0);
          if ( v7 == (_DWORD *)-1LL )
            goto LABEL_17;
          if ( *v7 == -1 )
          {
            v8 = this[7];
            v9 = (void *)SendMessageW(*v8, 0x150u, v6, 0);
            if ( v9 == (void *)-1LL )
              goto LABEL_17;
            operator delete(v9);
            if ( (unsigned int)SendMessageW(*v8, 0x144u, v6, 0) == -1 )
              goto LABEL_17;
            break;
          }
        }
        while ( ++v5 < v4 );
      }
    }
    pdwRenderingIntent = 0;
    if ( !WcsGetDefaultRenderingIntent(WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE, &pdwRenderingIntent) )
    {
      LastError = GetLastError();
      StringFromRC = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          StringFromRC = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_55;
      }
LABEL_17:
      StringFromRC = -2147467259;
      goto LABEL_55;
    }
    v12 = 0;
    while ( 1 )
    {
      v13 = v12;
      if ( LODWORD(qword_18001C9A0[v12]) == pdwRenderingIntent )
        break;
      if ( (unsigned int)++v12 >= 4 )
        goto LABEL_17;
    }
    v14 = (HINSTANCE)this[2];
    v34 = &NCoreLibrary::TString::gszNullState;
    v33 = 1735554163;
    StringFromRC = NCoreLibrary::TString::LoadStringFromRC((NCoreLibrary::TString *)&v33, v14, 0x7EBu);
    if ( StringFromRC < 0 )
    {
LABEL_19:
      NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v33);
      goto LABEL_55;
    }
    v15 = (HINSTANCE)this[2];
    v16 = HIDWORD(qword_18001C9A0[v13]);
    v35 = 1735554163;
    v36 = &NCoreLibrary::TString::gszNullState;
    StringFromRC = NCoreLibrary::TString::LoadStringFromRC((NCoreLibrary::TString *)&v35, v15, v16);
    if ( StringFromRC < 0 )
    {
LABEL_21:
      NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v35);
      goto LABEL_19;
    }
    v38 = &NCoreLibrary::TString::gszNullState;
    v37 = 1735554163;
    StringFromRC = NCoreLibrary::TString::Format((NCoreLibrary::TString *)&v37, v34, v36);
    if ( StringFromRC < 0 )
    {
LABEL_23:
      NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v37);
      goto LABEL_21;
    }
    v17 = operator new(4u);
    v2 = v17;
    if ( !v17 )
    {
      StringFromRC = -2147024882;
      goto LABEL_23;
    }
    v18 = (LPARAM)v38;
    *v17 = -1;
    v19 = this[7];
    v41 = 0;
    StringFromRC = Combo<unsigned long>::AddItem(v19, v18, (LPARAM)v17, &v41);
    if ( StringFromRC < 0 )
      goto LABEL_23;
    v2 = 0;
    v40 = 0;
    StringFromRC = ColorCplGetDefaultRenderingIntentScope(&v40);
    if ( StringFromRC < 0 )
      goto LABEL_23;
    if ( v40 == 1 )
    {
      v20 = 0;
    }
    else
    {
      v21 = v41;
      StringFromRC = 0;
      v22 = SendMessageW(*this[7], 0x14Eu, v41, 0);
      if ( v21 != -1 && (v22 == -1 || v21 != v22) )
      {
        NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v37);
        NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v35);
        NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v33);
        goto LABEL_17;
      }
      v20 = 1;
    }
    NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v37);
    NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v35);
    NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v33);
    if ( v20 )
      goto LABEL_55;
  }
  v23 = *((_DWORD *)this + 8);
  v40 = 0;
  v24 = 0;
  StringFromRC = -2147467259;
  if ( !WcsGetDefaultRenderingIntent(v23, &v40) )
  {
    v25 = GetLastError();
    v24 = v25;
    if ( v25 )
    {
      if ( v25 > 0 )
        v24 = (unsigned __int16)v25 | 0x80070000;
    }
    else
    {
      v24 = -2147467259;
    }
  }
  if ( v24 < 0 )
  {
    StringFromRC = v24;
  }
  else
  {
    v26 = SendMessageW(*this[7], 0x146u, 0, 0);
    v27 = v26;
    if ( v26 != -1 )
    {
      v28 = 0;
      if ( v26 > 0 )
      {
        do
        {
          v29 = (_DWORD *)SendMessageW(*this[7], 0x150u, v28, 0);
          if ( v29 == (_DWORD *)-1LL )
            break;
          if ( *v29 == v40 )
          {
            v30 = 0;
            v31 = SendMessageW(*this[7], 0x14Eu, v28, 0);
            if ( v28 != -1 && (v31 == -1 || v28 != v31) )
              v30 = -2147467259;
            StringFromRC = v30;
            break;
          }
          ++v28;
        }
        while ( v28 < v27 );
      }
    }
  }
  v2 = 0;
LABEL_55:
  operator delete(v2);
  return (unsigned int)StringFromRC;
}

```

## disassembly

```asm
0x180010404  mov     [rsp-28h+arg_18], rbx
0x180010409  push    rbp
0x18001040a  push    rsi
0x18001040b  push    rdi
0x18001040c  push    r14
0x18001040e  push    r15
0x180010410  mov     rbp, rsp
0x180010413  sub     rsp, 50h
0x180010417  cmp     dword ptr [rcx+20h], 1
0x18001041b  mov     r14, rcx
0x18001041e  jnz     loc_18001068E
0x180010424  mov     rcx, [rcx+38h]
0x180010428  xor     r9d, r9d; lParam
0x18001042b  xor     r8d, r8d; wParam
0x18001042e  mov     edx, 146h; Msg
0x180010433  xor     esi, esi
0x180010435  mov     rcx, [rcx]; hWnd
0x180010438  call    cs:__imp_SendMessageW
0x18001043e  mov     rdi, rax
0x180010441  cmp     eax, 0FFFFFFFFh
0x180010444  jz      short loc_1800104BD
0x180010446  xor     ebx, ebx
0x180010448  test    edi, edi
0x18001044a  jle     short loc_1800104BD
0x18001044c  mov     rcx, [r14+38h]
0x180010450  xor     r9d, r9d; lParam
0x180010453  movsxd  r15, ebx
0x180010456  mov     edx, 150h; Msg
0x18001045b  mov     r8, r15; wParam
0x18001045e  mov     rcx, [rcx]; hWnd
0x180010461  call    cs:__imp_SendMessageW
0x180010467  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001046b  jz      loc_18001050B
0x180010471  cmp     dword ptr [rax], 0FFFFFFFFh
0x180010474  jz      short loc_18001047E
0x180010476  inc     ebx
0x180010478  cmp     ebx, edi
0x18001047a  jl      short loc_18001044C
0x18001047c  jmp     short loc_1800104BD
0x18001047e  mov     rbx, [r14+38h]
0x180010482  xor     r9d, r9d; lParam
0x180010485  mov     r8, r15; wParam
0x180010488  mov     edx, 150h; Msg
0x18001048d  mov     rcx, [rbx]; hWnd
0x180010490  call    cs:__imp_SendMessageW
0x180010496  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001049a  jz      short loc_18001050B
0x18001049c  mov     rcx, rax; Block
0x18001049f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800104a4  mov     rcx, [rbx]; hWnd
0x1800104a7  xor     r9d, r9d; lParam
0x1800104aa  mov     r8, r15; wParam
0x1800104ad  mov     edx, 144h; Msg
0x1800104b2  call    cs:__imp_SendMessageW
0x1800104b8  cmp     eax, 0FFFFFFFFh
0x1800104bb  jz      short loc_18001050B
0x1800104bd  lea     rdx, [rbp+pdwRenderingIntent]; pdwRenderingIntent
0x1800104c1  mov     [rbp+pdwRenderingIntent], esi
0x1800104c4  xor     ecx, ecx; scope
0x1800104c6  call    cs:__imp_WcsGetDefaultRenderingIntent
0x1800104cc  test    eax, eax
0x1800104ce  jnz     short loc_1800104F0
0x1800104d0  call    cs:__imp_GetLastError
0x1800104d6  mov     ebx, eax
0x1800104d8  test    eax, eax
0x1800104da  jz      short loc_18001050B
0x1800104dc  jle     loc_180010759
0x1800104e2  movzx   ebx, ax
0x1800104e5  or      ebx, 80070000h
0x1800104eb  jmp     loc_180010759
0x1800104f0  mov     ecx, [rbp+pdwRenderingIntent]
0x1800104f3  lea     rdx, qword_18001C9A0
0x1800104fa  xor     eax, eax
0x1800104fc  movsxd  rdi, eax
0x1800104ff  cmp     [rdx+rdi*8], ecx
0x180010502  jz      short loc_180010515
0x180010504  inc     eax
0x180010506  cmp     eax, 4
0x180010509  jb      short loc_1800104FC
0x18001050b  mov     ebx, 80004005h
0x180010510  jmp     loc_180010759
0x180010515  mov     rdx, [r14+10h]; HINSTANCE
0x180010519  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x180010520  mov     r15d, 67727473h
0x180010526  mov     [rbp+var_28], rax
0x18001052a  mov     r8d, 7EBh; unsigned int
0x180010530  mov     [rbp+var_30], r15d
0x180010534  lea     rcx, [rbp+var_30]; this
0x180010538  call    ?LoadStringFromRC@TString@NCoreLibrary@@QEAAJPEAUHINSTANCE__@@I@Z; NCoreLibrary::TString::LoadStringFromRC(HINSTANCE__ *,uint)
0x18001053d  mov     ebx, eax
0x18001053f  test    eax, eax
0x180010541  jns     short loc_180010551
0x180010543  lea     rcx, [rbp+var_30]; this
0x180010547  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x18001054c  jmp     loc_180010759
0x180010551  mov     rdx, [r14+10h]; HINSTANCE
0x180010555  lea     r8, qword_18001C9A0
0x18001055c  mov     r8d, [r8+rdi*8+4]; unsigned int
0x180010561  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x180010568  lea     rcx, [rbp+var_20]; this
0x18001056c  mov     [rbp+var_20], r15d
0x180010570  mov     [rbp+var_18], rax
0x180010574  call    ?LoadStringFromRC@TString@NCoreLibrary@@QEAAJPEAUHINSTANCE__@@I@Z; NCoreLibrary::TString::LoadStringFromRC(HINSTANCE__ *,uint)
0x180010579  mov     ebx, eax
0x18001057b  test    eax, eax
0x18001057d  jns     short loc_18001058A
0x18001057f  lea     rcx, [rbp+var_20]; this
0x180010583  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x180010588  jmp     short loc_180010543
0x18001058a  mov     r8, [rbp+var_18]
0x18001058e  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x180010595  mov     rdx, [rbp+var_28]; unsigned __int16 *
0x180010599  lea     rcx, [rbp+var_10]; this
0x18001059d  mov     [rbp+var_8], rax
0x1800105a1  mov     [rbp+var_10], r15d
0x1800105a5  call    ?Format@TString@NCoreLibrary@@QEAAJPEBGZZ; NCoreLibrary::TString::Format(ushort const *,...)
0x1800105aa  mov     ebx, eax
0x1800105ac  test    eax, eax
0x1800105ae  jns     short loc_1800105BB
0x1800105b0  lea     rcx, [rbp+var_10]; this
0x1800105b4  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x1800105b9  jmp     short loc_18001057F
0x1800105bb  mov     ecx, 4; Size
0x1800105c0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800105c5  mov     rsi, rax
0x1800105c8  test    rax, rax
0x1800105cb  jnz     short loc_1800105D4
0x1800105cd  mov     ebx, 8007000Eh
0x1800105d2  jmp     short loc_1800105B0
0x1800105d4  mov     rdx, [rbp+var_8]
0x1800105d8  lea     r9, [rbp+arg_10]
0x1800105dc  mov     dword ptr [rax], 0FFFFFFFFh
0x1800105e2  mov     r8, rax
0x1800105e5  mov     rcx, [r14+38h]
0x1800105e9  mov     [rbp+arg_10], 0
0x1800105f0  call    ?AddItem@?$Combo@K@@QEAAJPEBGPEAKPEAH@Z; Combo<ulong>::AddItem(ushort const *,ulong *,int *)
0x1800105f5  mov     ebx, eax
0x1800105f7  test    eax, eax
0x1800105f9  js      short loc_1800105B0
0x1800105fb  xor     esi, esi
0x1800105fd  lea     rcx, [rbp+arg_8]
0x180010601  mov     [rbp+arg_8], esi
0x180010604  call    cs:__imp_ColorCplGetDefaultRenderingIntentScope
0x18001060a  mov     ebx, eax
0x18001060c  test    eax, eax
0x18001060e  js      short loc_1800105B0
0x180010610  cmp     [rbp+arg_8], 1
0x180010614  jnz     short loc_18001061A
0x180010616  xor     edi, edi
0x180010618  jmp     short loc_18001066B
0x18001061a  mov     rcx, [r14+38h]
0x18001061e  xor     r9d, r9d; lParam
0x180010621  movsxd  rdi, [rbp+arg_10]
0x180010625  mov     edx, 14Eh; Msg
0x18001062a  mov     r8, rdi; wParam
0x18001062d  xor     ebx, ebx
0x18001062f  mov     rcx, [rcx]; hWnd
0x180010632  call    cs:__imp_SendMessageW
0x180010638  cmp     edi, 0FFFFFFFFh
0x18001063b  jz      short loc_180010666
0x18001063d  cmp     eax, 0FFFFFFFFh
0x180010640  jz      short loc_180010646
0x180010642  cmp     edi, eax
0x180010644  jz      short loc_180010666
0x180010646  lea     rcx, [rbp+var_10]; this
0x18001064a  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x18001064f  lea     rcx, [rbp+var_20]; this
0x180010653  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x180010658  lea     rcx, [rbp+var_30]; this
0x18001065c  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x180010661  jmp     loc_18001050B
0x180010666  mov     edi, 1
0x18001066b  lea     rcx, [rbp+var_10]; this
0x18001066f  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x180010674  lea     rcx, [rbp+var_20]; this
0x180010678  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x18001067d  lea     rcx, [rbp+var_30]; this
0x180010681  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x180010686  test    edi, edi
0x180010688  jnz     loc_180010759
0x18001068e  mov     ecx, [r14+20h]; scope
0x180010692  lea     rdx, [rbp+arg_8]; pdwRenderingIntent
0x180010696  mov     [rbp+arg_8], 0
0x18001069d  xor     edi, edi
0x18001069f  call    cs:__imp_WcsGetDefaultRenderingIntent
0x1800106a5  mov     ebx, 80004005h
0x1800106aa  test    eax, eax
0x1800106ac  jnz     short loc_1800106C9
0x1800106ae  call    cs:__imp_GetLastError
0x1800106b4  mov     edi, eax
0x1800106b6  test    eax, eax
0x1800106b8  jz      short loc_1800106C7
0x1800106ba  jle     short loc_1800106C9
0x1800106bc  movzx   edi, ax
0x1800106bf  or      edi, 80070000h
0x1800106c5  jmp     short loc_1800106C9
0x1800106c7  mov     edi, ebx
0x1800106c9  test    edi, edi
0x1800106cb  js      loc_180010755
0x1800106d1  mov     rcx, [r14+38h]
0x1800106d5  xor     r9d, r9d; lParam
0x1800106d8  xor     r8d, r8d; wParam
0x1800106db  mov     edx, 146h; Msg
0x1800106e0  mov     rcx, [rcx]; hWnd
0x1800106e3  call    cs:__imp_SendMessageW
0x1800106e9  mov     rsi, rax
0x1800106ec  cmp     eax, 0FFFFFFFFh
0x1800106ef  jz      short loc_180010757
0x1800106f1  xor     edi, edi
0x1800106f3  test    esi, esi
0x1800106f5  jle     short loc_180010757
0x1800106f7  mov     rcx, [r14+38h]
0x1800106fb  xor     r9d, r9d; lParam
0x1800106fe  movsxd  r15, edi
0x180010701  mov     edx, 150h; Msg
0x180010706  mov     r8, r15; wParam
0x180010709  mov     rcx, [rcx]; hWnd
0x18001070c  call    cs:__imp_SendMessageW
0x180010712  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010716  jz      short loc_180010757
0x180010718  mov     ecx, [rbp+arg_8]
0x18001071b  cmp     [rax], ecx
0x18001071d  jz      short loc_180010727
0x18001071f  inc     edi
0x180010721  cmp     edi, esi
0x180010723  jl      short loc_1800106F7
0x180010725  jmp     short loc_180010757
0x180010727  mov     rcx, [r14+38h]
0x18001072b  xor     r9d, r9d; lParam
0x18001072e  mov     r8, r15; wParam
0x180010731  mov     edx, 14Eh; Msg
0x180010736  xor     esi, esi
0x180010738  mov     rcx, [rcx]; hWnd
0x18001073b  call    cs:__imp_SendMessageW
0x180010741  cmp     edi, 0FFFFFFFFh
0x180010744  jz      short loc_180010751
0x180010746  cmp     eax, 0FFFFFFFFh
0x180010749  jz      short loc_18001074F
0x18001074b  cmp     edi, eax
0x18001074d  jz      short loc_180010751
0x18001074f  mov     esi, ebx
0x180010751  mov     ebx, esi
0x180010753  jmp     short loc_180010757
0x180010755  mov     ebx, edi
0x180010757  xor     esi, esi
0x180010759  mov     rcx, rsi; Block
0x18001075c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010761  mov     eax, ebx
0x180010763  mov     rbx, [rsp+50h+arg_18]
0x18001076b  add     rsp, 50h
0x18001076f  pop     r15
0x180010771  pop     r14
0x180010773  pop     rdi
0x180010774  pop     rsi
0x180010775  pop     rbp
0x180010776  retn
```
