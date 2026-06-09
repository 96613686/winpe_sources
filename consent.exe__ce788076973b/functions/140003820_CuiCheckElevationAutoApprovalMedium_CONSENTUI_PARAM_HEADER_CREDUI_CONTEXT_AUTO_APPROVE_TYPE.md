# CuiCheckElevationAutoApprovalMedium(_CONSENTUI_PARAM_HEADER *,_CREDUI_CONTEXT *,_AUTO_APPROVE_TYPE *)

- ea: `0x140003820`
- end: `0x140003afa`
- name: `?CuiCheckElevationAutoApprovalMedium@@YAKPEAU_CONSENTUI_PARAM_HEADER@@PEAU_CREDUI_CONTEXT@@PEAW4_AUTO_APPROVE_TYPE@@@Z`
- size: `730`
- prototype: `__int64 __fastcall(struct _CONSENTUI_PARAM_HEADER *, struct _CREDUI_CONTEXT *, enum _AUTO_APPROVE_TYPE *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140003660`

## callees

- `0x140003820`
- `0x140003b00`
- `0x140003e40`
- `0x1400042e0`
- `0x14000f200`
- `0x14000fbec`
- `0x140013928`
- `0x140013950`
- `0x140013b04`
- `0x140013b50`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x1400039e8`
- `USER32!GetSystemMetrics` at `0x1400039e8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140003881`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140003881`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140003aab`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140003aab`
- `SHELL32!__imp_SHDefExtractIconW` at `0x140003a06`
- `SHELL32!__imp_SHDefExtractIconW` at `0x140003a06`
- `SHLWAPI!PathFindFileNameW` at `0x140003a11`
- `SHLWAPI!PathFindFileNameW` at `0x140003a11`
- `SHLWAPI!SHStrDupW` at `0x140003a1e`
- `SHLWAPI!SHStrDupW` at `0x140003a1e`

## pseudocode

```c
__int64 __fastcall CuiCheckElevationAutoApprovalMedium(
        struct _CONSENTUI_PARAM_HEADER *a1,
        struct _CREDUI_CONTEXT *a2,
        enum _AUTO_APPROVE_TYPE *a3)
{
  void *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rcx
  int v9; // eax
  const WCHAR *v10; // rbp
  int BinarySignature; // eax
  __int64 v12; // rbx
  unsigned __int16 SystemMetrics; // ax
  const WCHAR *FileNameW; // rax
  __int64 v16; // [rsp+60h] [rbp-58h] BYREF
  __int64 v17; // [rsp+68h] [rbp-50h] BYREF
  __int64 v18; // [rsp+70h] [rbp-48h] BYREF
  char v19; // [rsp+C0h] [rbp+8h] BYREF
  int v20; // [rsp+D0h] [rbp+18h] BYREF
  __int64 v21; // [rsp+D8h] [rbp+20h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    WPP_SF_ddDd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      11,
      a3,
      *((unsigned int *)a1 + 1),
      *((_DWORD *)a1 + 8),
      *((_DWORD *)a1 + 12),
      *(_DWORD *)a2);
  v6 = (void *)*((_QWORD *)a1 + 3);
  *(_DWORD *)a3 = 0;
  if ( ImpersonateLoggedOnUser(v6) )
  {
    v9 = *((_DWORD *)a1 + 1);
    if ( v9 )
    {
      if ( v9 == 1 )
      {
        if ( !(unsigned int)CuiIsCOMClassAutoApprovable((struct _GUID *)((char *)a1 + 232))
          || (int)CuiUpdateContextInformation(*((LPCWSTR *)a1 + 28), BYTE1(*((_DWORD *)a1 + 12)) & 1, a2) < 0
          || *(_DWORD *)a2 != 3
          || (*((_DWORD *)a1 + 12) & 0x100) == 0 )
        {
          goto LABEL_29;
        }
      }
      else if ( v9 != 2 )
      {
        goto LABEL_29;
      }
    }
    else
    {
      if ( (*((_DWORD *)a1 + 12) & 0x100) == 0 )
      {
        *(_DWORD *)a3 = 0;
        goto LABEL_29;
      }
      v10 = (const WCHAR *)*((_QWORD *)a1 + 29);
      if ( *v10 )
      {
        v19 = 1;
        v21 = 0;
        LOBYTE(v7) = 1;
        v16 = 0;
        v17 = 0;
        v20 = 0;
        v18 = 0;
        BinarySignature = CuiGetBinarySignature(v10, -1, v7, 0, 4096, &v20, &v19, &v21, &v16, &v17, &v18);
        if ( BinarySignature < 0 )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
            WPP_SF_D(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              19,
              WPP_bed9811735e730a365d52877ff824444_Traceguids,
              (unsigned int)BinarySignature);
          goto LABEL_29;
        }
        v12 = *((_QWORD *)a2 + 4);
        *((_QWORD *)a2 + 4) = 0;
        CuiFreeContextInformation(a2);
        *(_DWORD *)a2 = v20;
        *((_QWORD *)a2 + 3) = v21;
        *((_QWORD *)a2 + 2) = v16;
        *((_QWORD *)a2 + 8) = v17;
        *((_QWORD *)a2 + 9) = v18;
        *((_QWORD *)a2 + 4) = v12;
        *((_DWORD *)a2 + 15) = CuiGetBinaryLocation(v10);
        if ( *((_QWORD *)a2 + 2) )
        {
          SystemMetrics = GetSystemMetrics(11);
          SHDefExtractIconW(v10, 0, 0, (HICON *)a2 + 1, 0, SystemMetrics);
        }
        else
        {
          FileNameW = PathFindFileNameW(v10);
          SHStrDupW(FileNameW, (LPWSTR *)a2 + 2);
        }
        if ( *(_DWORD *)a2 != 3 )
        {
LABEL_29:
          RevertToSelf();
          goto LABEL_30;
        }
      }
    }
    *(_DWORD *)a3 = 1;
    goto LABEL_29;
  }
  v8 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return 0;
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_3d93b7323a903a71f6d346154c1b1bb3_Traceguids);
LABEL_30:
    v8 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v8 != &WPP_GLOBAL_Control && (*(_BYTE *)(v8 + 28) & 2) != 0 )
    WPP_SF_dd(
      *(_QWORD *)(v8 + 16),
      13,
      WPP_3d93b7323a903a71f6d346154c1b1bb3_Traceguids,
      *(unsigned int *)a3,
      *(_DWORD *)a2);
  return 0;
}

```

## disassembly

```asm
0x140003820  push    rbx
0x140003822  push    rsi
0x140003823  push    rdi
0x140003824  push    r12
0x140003826  push    r15
0x140003828  sub     rsp, 90h
0x14000382f  mov     rdi, r8
0x140003832  mov     rsi, rdx
0x140003835  mov     rbx, rcx
0x140003838  mov     rcx, cs:WPP_GLOBAL_Control
0x14000383f  lea     r15, WPP_GLOBAL_Control
0x140003846  cmp     rcx, r15
0x140003849  jz      short loc_140003877
0x14000384b  test    byte ptr [rcx+1Ch], 2
0x14000384f  jz      short loc_140003877
0x140003851  mov     eax, [rsi]
0x140003853  mov     edx, 0Bh
0x140003858  mov     r9d, [rbx+4]
0x14000385c  mov     rcx, [rcx+10h]
0x140003860  mov     dword ptr [rsp+0B8h+var_88], eax
0x140003864  mov     eax, [rbx+30h]
0x140003867  mov     [rsp+0B8h+nIconSize], eax
0x14000386b  mov     eax, [rbx+20h]
0x14000386e  mov     dword ptr [rsp+0B8h+phiconSmall], eax
0x140003872  call    WPP_SF_ddDd
0x140003877  mov     rcx, [rbx+18h]; hToken
0x14000387b  xor     r12d, r12d
0x14000387e  mov     [rdi], r12d
0x140003881  call    cs:__imp_ImpersonateLoggedOnUser
0x140003887  test    eax, eax
0x140003889  jnz     short loc_1400038BF
0x14000388b  mov     rcx, cs:WPP_GLOBAL_Control
0x140003892  cmp     rcx, r15
0x140003895  jz      loc_140003AE9
0x14000389b  test    byte ptr [rcx+1Ch], 2
0x14000389f  jz      loc_140003AC0
0x1400038a5  mov     rcx, [rcx+10h]
0x1400038a9  lea     r8, WPP_3d93b7323a903a71f6d346154c1b1bb3_Traceguids
0x1400038b0  mov     edx, 0Ch
0x1400038b5  call    WPP_SF_
0x1400038ba  jmp     loc_140003AB9
0x1400038bf  mov     eax, [rbx+4]
0x1400038c2  mov     [rsp+0B8h+var_30], rbp
0x1400038ca  test    eax, eax
0x1400038cc  jnz     loc_140003A5F
0x1400038d2  test    dword ptr [rbx+30h], 100h
0x1400038d9  jnz     short loc_1400038E3
0x1400038db  mov     [rdi], r12d
0x1400038de  jmp     loc_140003AAB
0x1400038e3  mov     rbp, [rbx+0E8h]
0x1400038ea  cmp     [rbp+0], r12w
0x1400038ef  jz      loc_140003AA5
0x1400038f5  lea     rax, [rsp+0B8h+var_48]
0x1400038fa  mov     [rsp+0B8h+arg_0], 1
0x140003902  mov     [rsp+0B8h+var_68], rax
0x140003907  xor     r9d, r9d
0x14000390a  lea     rax, [rsp+0B8h+var_50]
0x14000390f  mov     [rsp+0B8h+arg_18], r12
0x140003917  mov     [rsp+0B8h+var_70], rax
0x14000391c  mov     r8b, 1
0x14000391f  lea     rax, [rsp+0B8h+var_58]
0x140003924  mov     [rsp+0B8h+var_58], r12
0x140003929  mov     [rsp+0B8h+var_78], rax
0x14000392e  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x140003935  lea     rax, [rsp+0B8h+arg_18]
0x14000393d  mov     [rsp+0B8h+var_50], r12
0x140003942  mov     [rsp+0B8h+var_80], rax
0x140003947  mov     rcx, rbp
0x14000394a  lea     rax, [rsp+0B8h+arg_0]
0x140003952  mov     [rsp+0B8h+arg_10], r12d
0x14000395a  mov     [rsp+0B8h+var_88], rax
0x14000395f  lea     rax, [rsp+0B8h+arg_10]
0x140003967  mov     qword ptr [rsp+0B8h+nIconSize], rax
0x14000396c  mov     dword ptr [rsp+0B8h+phiconSmall], 1000h
0x140003974  mov     [rsp+0B8h+var_48], r12
0x140003979  call    ?CuiGetBinarySignature@@YAJPEBGPEAXEEW4SIGNATURE_INFO_FLAGS@@PEAW4_CONTEXT_SIGNATURE@@PEAEPEAPEAG5PEAPEBU_CERT_CONTEXT@@PEAPEAX@Z; CuiGetBinarySignature(ushort const *,void *,uchar,uchar,SIGNATURE_INFO_FLAGS,_CONTEXT_SIGNATURE *,uchar *,ushort * *,ushort * *,_CERT_CONTEXT const * *,void * *)
0x14000397e  test    eax, eax
0x140003980  js      loc_140003A33
0x140003986  mov     rbx, [rsi+20h]
0x14000398a  mov     rcx, rsi; struct _CREDUI_CONTEXT *
0x14000398d  mov     [rsi+20h], r12
0x140003991  mov     [rsp+0B8h+var_38], r14
0x140003999  call    ?CuiFreeContextInformation@@YAXPEAU_CREDUI_CONTEXT@@@Z; CuiFreeContextInformation(_CREDUI_CONTEXT *)
0x14000399e  mov     eax, [rsp+0B8h+arg_10]
0x1400039a5  mov     rcx, rbp
0x1400039a8  mov     [rsi], eax
0x1400039aa  mov     rax, [rsp+0B8h+arg_18]
0x1400039b2  mov     [rsi+18h], rax
0x1400039b6  mov     rax, [rsp+0B8h+var_58]
0x1400039bb  mov     [rsi+10h], rax
0x1400039bf  mov     rax, [rsp+0B8h+var_50]
0x1400039c4  mov     [rsi+40h], rax
0x1400039c8  mov     rax, [rsp+0B8h+var_48]
0x1400039cd  mov     [rsi+48h], rax
0x1400039d1  mov     [rsi+20h], rbx
0x1400039d5  call    ?CuiGetBinaryLocation@@YA?AW4_CONTEXT_FILE_LOCATION@@PEBG@Z; CuiGetBinaryLocation(ushort const *)
0x1400039da  mov     [rsi+3Ch], eax
0x1400039dd  cmp     [rsi+10h], r12
0x1400039e1  jz      short loc_140003A0E
0x1400039e3  mov     ecx, 0Bh; nIndex
0x1400039e8  call    cs:__imp_GetSystemMetrics
0x1400039ee  movzx   edx, ax
0x1400039f1  lea     r9, [rsi+8]; phiconLarge
0x1400039f5  mov     [rsp+0B8h+nIconSize], edx; nIconSize
0x1400039f9  xor     r8d, r8d; uFlags
0x1400039fc  xor     edx, edx; iIndex
0x1400039fe  mov     [rsp+0B8h+phiconSmall], r12; phiconSmall
0x140003a03  mov     rcx, rbp; pszIconFile
0x140003a06  call    cs:__imp_SHDefExtractIconW
0x140003a0c  jmp     short loc_140003A24
0x140003a0e  mov     rcx, rbp; pszPath
0x140003a11  call    cs:__imp_PathFindFileNameW
0x140003a17  mov     rcx, rax; psz
0x140003a1a  lea     rdx, [rsi+10h]; ppwsz
0x140003a1e  call    cs:__imp_SHStrDupW
0x140003a24  cmp     dword ptr [rsi], 3
0x140003a27  mov     r14, [rsp+0B8h+var_38]
0x140003a2f  jnz     short loc_140003AAB
0x140003a31  jmp     short loc_140003AA5
0x140003a33  mov     rcx, cs:WPP_GLOBAL_Control
0x140003a3a  cmp     rcx, r15
0x140003a3d  jz      short loc_140003AAB
0x140003a3f  test    byte ptr [rcx+1Ch], 2
0x140003a43  jz      short loc_140003AAB
0x140003a45  mov     rcx, [rcx+10h]
0x140003a49  lea     r8, WPP_bed9811735e730a365d52877ff824444_Traceguids
0x140003a50  mov     edx, 13h
0x140003a55  mov     r9d, eax
0x140003a58  call    WPP_SF_D
0x140003a5d  jmp     short loc_140003AAB
0x140003a5f  cmp     eax, 1
0x140003a62  jnz     short loc_140003AA0
0x140003a64  lea     rcx, [rbx+0E8h]; struct _GUID *
0x140003a6b  call    ?CuiIsCOMClassAutoApprovable@@YAHPEAU_GUID@@@Z; CuiIsCOMClassAutoApprovable(_GUID *)
0x140003a70  test    eax, eax
0x140003a72  jz      short loc_140003AAB
0x140003a74  mov     edx, [rbx+30h]
0x140003a77  mov     r8, rsi; struct _CREDUI_CONTEXT *
0x140003a7a  mov     rcx, [rbx+0E0h]; pszPath
0x140003a81  shr     edx, 8
0x140003a84  and     dl, 1; unsigned __int8
0x140003a87  call    ?CuiUpdateContextInformation@@YAJPEBGEPEAU_CREDUI_CONTEXT@@@Z; CuiUpdateContextInformation(ushort const *,uchar,_CREDUI_CONTEXT *)
0x140003a8c  test    eax, eax
0x140003a8e  js      short loc_140003AAB
0x140003a90  cmp     dword ptr [rsi], 3
0x140003a93  jnz     short loc_140003AAB
0x140003a95  test    dword ptr [rbx+30h], 100h
0x140003a9c  jz      short loc_140003AAB
0x140003a9e  jmp     short loc_140003AA5
0x140003aa0  cmp     eax, 2
0x140003aa3  jnz     short loc_140003AAB
0x140003aa5  mov     dword ptr [rdi], 1
0x140003aab  call    cs:__imp_RevertToSelf
0x140003ab1  mov     rbp, [rsp+0B8h+var_30]
0x140003ab9  mov     rcx, cs:WPP_GLOBAL_Control
0x140003ac0  cmp     rcx, r15
0x140003ac3  jz      short loc_140003AE9
0x140003ac5  test    byte ptr [rcx+1Ch], 2
0x140003ac9  jz      short loc_140003AE9
0x140003acb  mov     eax, [rsi]
0x140003acd  lea     r8, WPP_3d93b7323a903a71f6d346154c1b1bb3_Traceguids
0x140003ad4  mov     r9d, [rdi]
0x140003ad7  mov     edx, 0Dh
0x140003adc  mov     rcx, [rcx+10h]
0x140003ae0  mov     dword ptr [rsp+0B8h+phiconSmall], eax
0x140003ae4  call    WPP_SF_dd
0x140003ae9  xor     eax, eax
0x140003aeb  add     rsp, 90h
0x140003af2  pop     r15
0x140003af4  pop     r12
0x140003af6  pop     rdi
0x140003af7  pop     rsi
0x140003af8  pop     rbx
0x140003af9  retn
```
