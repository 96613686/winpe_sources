# SetAccountInformationDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180010710`
- end: `0x180010b56`
- name: `?SetAccountInformationDlgProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `1094`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001840`
- `0x180009ef8`
- `0x180009f38`
- `0x18000cae0`
- `0x1800104c4`
- `0x18001056c`
- `0x180010710`
- `0x180017e90`
- `0x18001aa9a`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180010863`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180010863`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010870`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010904`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010955`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010a17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010870`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010904`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010955`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010a17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800107f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800107f6`
- `USER32!SendMessageW` at `0x180010a5d`
- `USER32!SendMessageW` at `0x180010a7a`
- `USER32!SendMessageW` at `0x180010a98`
- `USER32!SendMessageW` at `0x180010a5d`
- `USER32!SendMessageW` at `0x180010a7a`
- `USER32!SendMessageW` at `0x180010a98`
- `USER32!GetDlgItem` at `0x180010a44`
- `USER32!GetDlgItem` at `0x180010a69`
- `USER32!GetDlgItem` at `0x180010a87`
- `USER32!GetDlgItem` at `0x180010a44`
- `USER32!GetDlgItem` at `0x180010a69`
- `USER32!GetDlgItem` at `0x180010a87`
- `USER32!GetDlgItemTextW` at `0x1800107db`
- `USER32!GetDlgItemTextW` at `0x180010831`
- `USER32!GetDlgItemTextW` at `0x18001084f`
- `USER32!GetDlgItemTextW` at `0x1800107db`
- `USER32!GetDlgItemTextW` at `0x180010831`
- `USER32!GetDlgItemTextW` at `0x18001084f`
- `USER32!SetDlgItemTextW` at `0x180010af2`
- `USER32!SetDlgItemTextW` at `0x180010b09`
- `USER32!SetDlgItemTextW` at `0x180010b22`
- `USER32!SetDlgItemTextW` at `0x180010af2`
- `USER32!SetDlgItemTextW` at `0x180010b09`
- `USER32!SetDlgItemTextW` at `0x180010b22`
- `USER32!EndDialog` at `0x18001091d`
- `USER32!EndDialog` at `0x18001091d`

## pseudocode

```c
INT_PTR __fastcall SetAccountInformationDlgProc(HWND a1, int a2, INT_PTR a3, __int64 a4)
{
  int v8; // ebx
  UINT DlgItemTextW; // eax
  unsigned int v11; // r8d
  unsigned __int16 *v12; // r9
  __int64 v13; // r15
  unsigned __int16 *v14; // rax
  unsigned int v15; // r8d
  unsigned __int16 *v16; // r9
  unsigned __int16 *v17; // rsi
  UINT v18; // r13d
  int v19; // edx
  __int64 v20; // r15
  unsigned __int64 v21; // r13
  __int64 v22; // r10
  WCHAR *p_String1; // rax
  __int64 v24; // rcx
  WCHAR *p_String2; // rax
  int v26; // edx
  unsigned __int16 *v27; // rax
  __int64 v28; // rcx
  const WCHAR *v29; // rax
  __int64 i; // r15
  __int64 v31; // r10
  HWND DlgItem; // rax
  HWND v33; // rax
  HWND v34; // rax
  unsigned __int16 *v35; // [rsp+30h] [rbp-D0h]
  WCHAR String; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v37[526]; // [rsp+42h] [rbp-BEh] BYREF
  WCHAR String1; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v39[526]; // [rsp+252h] [rbp+152h] BYREF
  WCHAR String2; // [rsp+460h] [rbp+360h] BYREF
  _BYTE v41[526]; // [rsp+462h] [rbp+362h] BYREF
  unsigned __int16 v42; // [rsp+670h] [rbp+570h] BYREF
  _BYTE v43[526]; // [rsp+672h] [rbp+572h] BYREF

  String = 0;
  memset_0(v37, 0, 0x200u);
  String1 = 0;
  memset_0(v39, 0, 0x200u);
  String2 = 0;
  memset_0(v41, 0, 0x200u);
  v8 = a2 - 272;
  if ( v8 )
  {
    if ( v8 != 1 )
      return 0;
    if ( (unsigned __int16)a3 != 1 )
    {
      if ( (unsigned __int16)a3 != 2 )
        return 0;
      goto LABEL_22;
    }
    String = 0;
    DlgItemTextW = GetDlgItemTextW(a1, 1008, &String, 257);
    if ( !String )
    {
      v19 = 4149;
      goto LABEL_10;
    }
    v13 = DlgItemTextW + 1;
    v14 = (unsigned __int16 *)CoTaskMemAlloc(2 * v13);
    v17 = v14;
    if ( v14 )
    {
      *v14 = 0;
      StringCchCopyW(v14, (unsigned int)v13, &String);
      v18 = GetDlgItemTextW(a1, 1011, &String1, 257);
      GetDlgItemTextW(a1, 1012, &String2, 257);
      if ( lstrcmpW(&String1, &String2) )
      {
        CoTaskMemFree(v17);
        v19 = 4134;
LABEL_10:
        SchedUIMessageDialog(a1, v19, v11, v12);
        return 1;
      }
      v20 = -1;
      if ( v18 )
      {
        v21 = v18 + 1;
        v35 = (unsigned __int16 *)operator new(saturated_mul(v21, 2u));
        if ( v35 )
        {
          *v35 = 0;
          StringCchCopyW(v35, (unsigned int)v21, &String1);
          v22 = 514;
          p_String1 = &String1;
          v24 = 514;
          do
          {
            *(_BYTE *)p_String1 = 0;
            p_String1 = (WCHAR *)((char *)p_String1 + 1);
            --v24;
          }
          while ( v24 );
          p_String2 = &String2;
          do
          {
            *(_BYTE *)p_String2 = 0;
            p_String2 = (WCHAR *)((char *)p_String2 + 1);
            --v22;
          }
          while ( v22 );
          goto LABEL_25;
        }
      }
      else
      {
        v27 = (unsigned __int16 *)operator new(2u);
        v35 = v27;
        if ( v27 )
        {
          *v27 = 0;
LABEL_25:
          v28 = qword_180023EE0;
          if ( *(_QWORD *)qword_180023EE0 )
          {
            CoTaskMemFree(*(LPVOID *)qword_180023EE0);
            v28 = qword_180023EE0;
            *(_QWORD *)qword_180023EE0 = 0;
          }
          v29 = *(const WCHAR **)(v28 + 8);
          if ( v29 && v29 != &::String )
          {
            do
              ++v20;
            while ( v29[v20] );
            for ( i = 2 * v20 + 2; i; --i )
            {
              *(_BYTE *)v29 = 0;
              v29 = (const WCHAR *)((char *)v29 + 1);
            }
            operator delete(*(void **)(v28 + 8));
            *(_QWORD *)(qword_180023EE0 + 8) = 0;
          }
          v42 = 0;
          memset_0(v43, 0, 0x200u);
          if ( (int)TranslateAccount(1, v17, &v42) >= 0 )
          {
            StringCchCopyW(v17, 0x101u, &v42);
            v31 = qword_180023EE0;
            *(_QWORD *)qword_180023EE0 = v17;
            *(_QWORD *)(v31 + 8) = v35;
            goto LABEL_22;
          }
          CoTaskMemFree(v17);
          v26 = 4133;
LABEL_21:
          SchedUIMessageDialog(a1, v26, v15, v16);
LABEL_22:
          EndDialog(a1, a3);
          return 1;
        }
      }
      CoTaskMemFree(v17);
    }
    v26 = 4135;
    goto LABEL_21;
  }
  qword_180023EE0 = a4;
  DlgItem = GetDlgItem(a1, 1011);
  SendMessageW(DlgItem, 0xC5u, 0x100u, 0);
  v33 = GetDlgItem(a1, 1011);
  SendMessageW(v33, 0xC5u, 0x100u, 0);
  v34 = GetDlgItem(a1, 1012);
  SendMessageW(v34, 0xC5u, 0x100u, 0);
  if ( *(_QWORD *)qword_180023EE0 )
  {
    if ( (int)TranslateAccount(0, *(_QWORD *)qword_180023EE0, &String) < 0 )
      StringCchCopyW(&String, 0x101u, *(const unsigned __int16 **)qword_180023EE0);
  }
  else
  {
    GetDefaultDomainAndUserName(&String, 0);
  }
  SetDlgItemTextW(a1, 1008, &String);
  SetDlgItemTextW(a1, 1011, *(LPCWSTR *)(qword_180023EE0 + 8));
  SetDlgItemTextW(a1, 1012, *(LPCWSTR *)(qword_180023EE0 + 8));
  CenterDialog(a1);
  return 1;
}

```

## disassembly

```asm
0x180010710  push    rbp
0x180010712  push    rbx
0x180010713  push    rsi
0x180010714  push    rdi
0x180010715  push    r13
0x180010717  push    r14
0x180010719  push    r15
0x18001071b  lea     rbp, [rsp-790h]
0x180010723  sub     rsp, 890h
0x18001072a  mov     rax, cs:__security_cookie
0x180010731  xor     rax, rsp
0x180010734  mov     [rbp+7C0h+var_40], rax
0x18001073b  mov     r14, r8
0x18001073e  mov     ebx, edx
0x180010740  mov     rdi, rcx
0x180010743  mov     r15d, 200h
0x180010749  xor     r13d, r13d
0x18001074c  lea     rcx, [rsp+8C0h+var_87E]; void *
0x180010751  mov     r8d, r15d; Size
0x180010754  mov     [rsp+8C0h+String], r13w
0x18001075a  xor     edx, edx; Val
0x18001075c  mov     rsi, r9
0x18001075f  call    memset_0
0x180010764  mov     r8d, r15d; Size
0x180010767  mov     [rbp+7C0h+String1], r13w
0x18001076f  xor     edx, edx; Val
0x180010771  lea     rcx, [rbp+7C0h+var_66E]; void *
0x180010778  call    memset_0
0x18001077d  mov     r8d, r15d; Size
0x180010780  mov     [rbp+7C0h+String2], r13w
0x180010788  xor     edx, edx; Val
0x18001078a  lea     rcx, [rbp+7C0h+var_45E]; void *
0x180010791  call    memset_0
0x180010796  sub     ebx, 110h
0x18001079c  jz      loc_180010A31
0x1800107a2  cmp     ebx, 1
0x1800107a5  jnz     short loc_1800107BB
0x1800107a7  movzx   ecx, r14w
0x1800107ab  lea     ebx, [r13+1]
0x1800107af  sub     ecx, ebx
0x1800107b1  jz      short loc_1800107C2
0x1800107b3  cmp     ecx, ebx
0x1800107b5  jz      loc_180010917
0x1800107bb  xor     eax, eax
0x1800107bd  jmp     loc_180010B35
0x1800107c2  mov     r9d, 101h; cchMax
0x1800107c8  mov     [rsp+8C0h+String], r13w
0x1800107ce  lea     r8, [rsp+8C0h+String]; lpString
0x1800107d3  mov     edx, 3F0h; nIDDlgItem
0x1800107d8  mov     rcx, rdi; hDlg
0x1800107db  call    cs:__imp_GetDlgItemTextW
0x1800107e1  cmp     [rsp+8C0h+String], r13w
0x1800107e7  jz      loc_180010A27
0x1800107ed  inc     eax
0x1800107ef  mov     r15d, eax
0x1800107f2  lea     rcx, [rax+rax]; cb
0x1800107f6  call    cs:__imp_CoTaskMemAlloc
0x1800107fc  mov     rsi, rax
0x1800107ff  test    rax, rax
0x180010802  jz      loc_18001090A
0x180010808  lea     r8, [rsp+8C0h+String]; unsigned __int16 *
0x18001080d  mov     [rax], r13w
0x180010811  mov     edx, r15d; unsigned __int64
0x180010814  mov     rcx, rax; unsigned __int16 *
0x180010817  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001081c  mov     r9d, 101h; cchMax
0x180010822  lea     r8, [rbp+7C0h+String1]; lpString
0x180010829  mov     edx, 3F3h; nIDDlgItem
0x18001082e  mov     rcx, rdi; hDlg
0x180010831  call    cs:__imp_GetDlgItemTextW
0x180010837  mov     r9d, 101h; cchMax
0x18001083d  lea     r8, [rbp+7C0h+String2]; lpString
0x180010844  mov     edx, 3F4h; nIDDlgItem
0x180010849  mov     rcx, rdi; hDlg
0x18001084c  mov     r13d, eax
0x18001084f  call    cs:__imp_GetDlgItemTextW
0x180010855  lea     rdx, [rbp+7C0h+String2]; lpString2
0x18001085c  lea     rcx, [rbp+7C0h+String1]; lpString1
0x180010863  call    cs:__imp_lstrcmpW
0x180010869  test    eax, eax
0x18001086b  jz      short loc_18001088B
0x18001086d  mov     rcx, rsi; pv
0x180010870  call    cs:__imp_CoTaskMemFree
0x180010876  mov     edx, 1026h; int
0x18001087b  mov     rcx, rdi; HWND
0x18001087e  call    ?SchedUIMessageDialog@@YAHPEAUHWND__@@HIPEAG@Z; SchedUIMessageDialog(HWND__ *,int,uint,ushort *)
0x180010883  mov     rax, rbx
0x180010886  jmp     loc_180010B35
0x18001088b  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001088f  test    r13d, r13d
0x180010892  jz      loc_180010928
0x180010898  inc     r13d
0x18001089b  lea     eax, [r15+3]
0x18001089f  mul     r13
0x1800108a2  cmovb   rax, r15
0x1800108a6  mov     rcx, rax; Size
0x1800108a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800108ae  mov     [rsp+8C0h+var_890], rax
0x1800108b3  mov     rcx, rax; unsigned __int16 *
0x1800108b6  test    rax, rax
0x1800108b9  jz      short loc_180010901
0x1800108bb  xor     eax, eax
0x1800108bd  lea     r8, [rbp+7C0h+String1]; unsigned __int16 *
0x1800108c4  mov     edx, r13d; unsigned __int64
0x1800108c7  mov     [rcx], ax
0x1800108ca  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800108cf  mov     r10d, 202h
0x1800108d5  lea     rax, [rbp+7C0h+String1]
0x1800108dc  mov     ecx, r10d
0x1800108df  xor     r13d, r13d
0x1800108e2  mov     [rax], r13b
0x1800108e5  add     rax, rbx
0x1800108e8  sub     rcx, rbx
0x1800108eb  jnz     short loc_1800108E2
0x1800108ed  lea     rax, [rbp+7C0h+String2]
0x1800108f4  mov     [rax], r13b
0x1800108f7  add     rax, rbx
0x1800108fa  sub     r10, rbx
0x1800108fd  jnz     short loc_1800108F4
0x1800108ff  jmp     short loc_180010943
0x180010901  mov     rcx, rsi; pv
0x180010904  call    cs:__imp_CoTaskMemFree
0x18001090a  mov     edx, 1027h; int
0x18001090f  mov     rcx, rdi; HWND
0x180010912  call    ?SchedUIMessageDialog@@YAHPEAUHWND__@@HIPEAG@Z; SchedUIMessageDialog(HWND__ *,int,uint,ushort *)
0x180010917  mov     rdx, r14; nResult
0x18001091a  mov     rcx, rdi; hDlg
0x18001091d  call    cs:__imp_EndDialog
0x180010923  jmp     loc_180010883
0x180010928  mov     ecx, 2; Size
0x18001092d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010932  xor     r13d, r13d
0x180010935  mov     [rsp+8C0h+var_890], rax
0x18001093a  test    rax, rax
0x18001093d  jz      short loc_180010901
0x18001093f  mov     [rax], r13w
0x180010943  mov     rcx, cs:qword_180023EE0
0x18001094a  mov     rax, [rcx]
0x18001094d  test    rax, rax
0x180010950  jz      short loc_180010965
0x180010952  mov     rcx, rax; pv
0x180010955  call    cs:__imp_CoTaskMemFree
0x18001095b  mov     rcx, cs:qword_180023EE0
0x180010962  mov     [rcx], r13
0x180010965  mov     rax, [rcx+8]
0x180010969  test    rax, rax
0x18001096c  jz      short loc_1800109B0
0x18001096e  lea     rdx, String
0x180010975  cmp     rax, rdx
0x180010978  jz      short loc_1800109B0
0x18001097a  inc     r15
0x18001097d  cmp     [rax+r15*2], r13w
0x180010982  jnz     short loc_18001097A
0x180010984  lea     r15, ds:2[r15*2]
0x18001098c  test    r15, r15
0x18001098f  jz      short loc_18001099C
0x180010991  mov     [rax], r13b
0x180010994  add     rax, rbx
0x180010997  sub     r15, rbx
0x18001099a  jnz     short loc_180010991
0x18001099c  mov     rcx, [rcx+8]; Block
0x1800109a0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800109a5  mov     rax, cs:qword_180023EE0
0x1800109ac  mov     [rax+8], r13
0x1800109b0  xor     edx, edx; Val
0x1800109b2  mov     [rbp+7C0h+var_250], r13w
0x1800109ba  mov     r8d, 200h; Size
0x1800109c0  lea     rcx, [rbp+7C0h+var_24E]; void *
0x1800109c7  call    memset_0
0x1800109cc  lea     rax, [rsp+8C0h+var_890]
0x1800109d1  mov     rdx, rsi
0x1800109d4  lea     r8, [rbp+7C0h+var_250]
0x1800109db  mov     [rsp+8C0h+var_8A0], rax
0x1800109e0  mov     ecx, ebx
0x1800109e2  call    ?TranslateAccount@@YAJW4_TRANSLATION_DIRECTION@@PEBGPEAGKPEAPEAG@Z; TranslateAccount(_TRANSLATION_DIRECTION,ushort const *,ushort *,ulong,ushort * *)
0x1800109e7  mov     rcx, rsi; unsigned __int16 *
0x1800109ea  test    eax, eax
0x1800109ec  js      short loc_180010A17
0x1800109ee  lea     r8, [rbp+7C0h+var_250]; unsigned __int16 *
0x1800109f5  mov     edx, 101h; unsigned __int64
0x1800109fa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800109ff  mov     r10, cs:qword_180023EE0
0x180010a06  mov     rax, [rsp+8C0h+var_890]
0x180010a0b  mov     [r10], rsi
0x180010a0e  mov     [r10+8], rax
0x180010a12  jmp     loc_180010917
0x180010a17  call    cs:__imp_CoTaskMemFree
0x180010a1d  mov     edx, 1025h
0x180010a22  jmp     loc_18001090F
0x180010a27  mov     edx, 1035h
0x180010a2c  jmp     loc_18001087B
0x180010a31  mov     r15d, 3F3h
0x180010a37  mov     cs:qword_180023EE0, rsi
0x180010a3e  mov     edx, r15d; nIDDlgItem
0x180010a41  mov     rcx, rdi; hDlg
0x180010a44  call    cs:__imp_GetDlgItem
0x180010a4a  mov     esi, 100h
0x180010a4f  xor     r9d, r9d; lParam
0x180010a52  mov     rcx, rax; hWnd
0x180010a55  mov     r8d, esi; wParam
0x180010a58  lea     ebx, [rsi-3Bh]
0x180010a5b  mov     edx, ebx; Msg
0x180010a5d  call    cs:__imp_SendMessageW
0x180010a63  mov     edx, r15d; nIDDlgItem
0x180010a66  mov     rcx, rdi; hDlg
0x180010a69  call    cs:__imp_GetDlgItem
0x180010a6f  xor     r9d, r9d; lParam
0x180010a72  mov     r8d, esi; wParam
0x180010a75  mov     rcx, rax; hWnd
0x180010a78  mov     edx, ebx; Msg
0x180010a7a  call    cs:__imp_SendMessageW
0x180010a80  lea     edx, [r15+1]; nIDDlgItem
0x180010a84  mov     rcx, rdi; hDlg
0x180010a87  call    cs:__imp_GetDlgItem
0x180010a8d  xor     r9d, r9d; lParam
0x180010a90  mov     r8d, esi; wParam
0x180010a93  mov     rcx, rax; hWnd
0x180010a96  mov     edx, ebx; Msg
0x180010a98  call    cs:__imp_SendMessageW
0x180010a9e  mov     rax, cs:qword_180023EE0
0x180010aa5  mov     rdx, [rax]; unsigned int
0x180010aa8  test    rdx, rdx
0x180010aab  jz      short loc_180010ADB
0x180010aad  lea     r8, [rsp+8C0h+String]
0x180010ab2  mov     [rsp+8C0h+var_8A0], r13
0x180010ab7  xor     ecx, ecx
0x180010ab9  call    ?TranslateAccount@@YAJW4_TRANSLATION_DIRECTION@@PEBGPEAGKPEAPEAG@Z; TranslateAccount(_TRANSLATION_DIRECTION,ushort const *,ushort *,ulong,ushort * *)
0x180010abe  test    eax, eax
0x180010ac0  jns     short loc_180010AE5
0x180010ac2  mov     r8, cs:qword_180023EE0
0x180010ac9  lea     edx, [rsi+1]; unsigned __int64
0x180010acc  lea     rcx, [rsp+8C0h+String]; unsigned __int16 *
0x180010ad1  mov     r8, [r8]; unsigned __int16 *
0x180010ad4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010ad9  jmp     short loc_180010AE5
0x180010adb  lea     rcx, [rsp+8C0h+String]; lpNameBuffer
0x180010ae0  call    ?GetDefaultDomainAndUserName@@YAXPEAGK@Z; GetDefaultDomainAndUserName(ushort *,ulong)
0x180010ae5  lea     r8, [rsp+8C0h+String]; lpString
0x180010aea  mov     edx, 3F0h; nIDDlgItem
0x180010aef  mov     rcx, rdi; hDlg
0x180010af2  call    cs:__imp_SetDlgItemTextW
0x180010af8  mov     r8, cs:qword_180023EE0
0x180010aff  mov     edx, r15d; nIDDlgItem
0x180010b02  mov     rcx, rdi; hDlg
0x180010b05  mov     r8, [r8+8]; lpString
0x180010b09  call    cs:__imp_SetDlgItemTextW
0x180010b0f  mov     r8, cs:qword_180023EE0
0x180010b16  mov     edx, 3F4h; nIDDlgItem
0x180010b1b  mov     rcx, rdi; hDlg
0x180010b1e  mov     r8, [r8+8]; lpString
0x180010b22  call    cs:__imp_SetDlgItemTextW
0x180010b28  mov     rcx, rdi; hWnd
0x180010b2b  call    ?CenterDialog@@YAXPEAUHWND__@@@Z; CenterDialog(HWND__ *)
0x180010b30  mov     eax, 1
0x180010b35  mov     rcx, [rbp+7C0h+var_40]
0x180010b3c  xor     rcx, rsp; StackCookie
0x180010b3f  call    __security_check_cookie
0x180010b44  add     rsp, 890h
0x180010b4b  pop     r15
0x180010b4d  pop     r14
0x180010b4f  pop     r13
0x180010b51  pop     rdi
0x180010b52  pop     rsi
0x180010b53  pop     rbx
0x180010b54  pop     rbp
0x180010b55  retn
```
