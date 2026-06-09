# CscDel_ShouldDelete(ushort const *,void *,ulong,tagOFFLINEFILES_ITEM_DESCRIPTOR const &)

- ea: `0x18004aa6c`
- end: `0x18004ae31`
- name: `?CscDel_ShouldDelete@@YAHPEBGPEAXKAEBUtagOFFLINEFILES_ITEM_DESCRIPTOR@@@Z`
- size: `965`
- prototype: `__int64 __fastcall(PCWSTR SourceString, void *, unsigned int, const struct tagOFFLINEFILES_ITEM_DESCRIPTOR *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004a4c8`
- `0x18004ae9c`

## callees

- `0x18001b82c`
- `0x18002a958`
- `0x18002f10c`
- `0x180033d44`
- `0x18003c488`
- `0x18003e928`
- `0x1800469c0`
- `0x18004aa6c`
- `0x18004af6c`
- `0x180080b88`
- `0x180080d34`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ad75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004adb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ad75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004adb8`
- `KERNEL32!LocalFree` at `0x18004ad83`
- `KERNEL32!LocalFree` at `0x18004adc6`
- `KERNEL32!LocalFree` at `0x18004ad83`
- `KERNEL32!LocalFree` at `0x18004adc6`
- `ADVAPI32!SetThreadToken` at `0x18004ad62`
- `ADVAPI32!SetThreadToken` at `0x18004ada5`
- `ADVAPI32!SetThreadToken` at `0x18004ad62`
- `ADVAPI32!SetThreadToken` at `0x18004ada5`

## pseudocode

```c
__int64 __fastcall CscDel_ShouldDelete(
        PCWSTR SourceString,
        void *a2,
        char a3,
        const struct tagOFFLINEFILES_ITEM_DESCRIPTOR *a4)
{
  int IsItemPinned; // eax
  __int64 v9; // r9
  CObjectMonitor *v10; // r10
  int v11; // r13d
  CObjectMonitor *v12; // rcx
  __int64 v13; // rdx
  int v14; // edi
  int v15; // r14d
  int v16; // r12d
  const unsigned __int16 *v17; // rax
  CObjectMonitor *v18; // rcx
  int v19; // edi
  unsigned int v20; // esi
  unsigned int v22; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v23; // [rsp+34h] [rbp-1Ch] BYREF
  HANDLE Token; // [rsp+38h] [rbp-18h] BYREF
  void *v25; // [rsp+40h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-8h]
  unsigned __int16 v27; // [rsp+A0h] [rbp+50h] BYREF
  const struct tagOFFLINEFILES_ITEM_DESCRIPTOR *v28; // [rsp+A8h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0 )
  {
    WPP_SF_SqD(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)a2, a3, (_DWORD)SourceString, (char)a2, a3);
  }
  v28 = a4;
  IsItemPinned = CCacheItemInfo::IsItemPinned((CCacheItemInfo *)&v28);
  v11 = IsItemPinned;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != v10 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0 )
  {
    WPP_SF_DDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_37cedf518d6f395f1417435d625f7a12_Traceguids,
      v9,
      (a3 & 1) == 0,
      IsItemPinned);
    v12 = WPP_GLOBAL_Control;
    v10 = (CObjectMonitor *)&WPP_GLOBAL_Control;
  }
  if ( v11 )
  {
    if ( (a3 & 2) != 0 )
      goto LABEL_9;
  }
  else if ( (a3 & 1) != 0 )
  {
LABEL_9:
    if ( (*((_DWORD *)a4 + 1) & 0x800000) != 0 )
    {
      if ( v12 == v10 || (*((_DWORD *)v12 + 7) & 0x4000) == 0 )
        return 1;
      v13 = 18;
LABEL_13:
      WPP_SF_S(*((_QWORD *)v12 + 2), v13, WPP_37cedf518d6f395f1417435d625f7a12_Traceguids, SourceString);
      return 1;
    }
    goto LABEL_59;
  }
  if ( (*((_BYTE *)a4 + 4) & 1) != 0
    || (*((_BYTE *)a4 + 4) & 0x10) != 0
    || (v14 = 0, (*((_DWORD *)a4 + 1) & 0x400) != 0) )
  {
    v14 = 1;
  }
  v15 = a3 & 4;
  v16 = *((_DWORD *)a4 + 30) & 6;
  if ( v12 != v10 && (*((_DWORD *)v12 + 7) & 0x4000) != 0 )
  {
    WPP_SF_DDD(*((_QWORD *)v12 + 2), 12, WPP_37cedf518d6f395f1417435d625f7a12_Traceguids, v16 == 6, v14, v15 != 0);
    v12 = WPP_GLOBAL_Control;
    v10 = (CObjectMonitor *)&WPP_GLOBAL_Control;
  }
  if ( !v14 || v15 || v16 == 6 )
  {
    if ( !a2 )
    {
      if ( v12 == v10 || (*((_DWORD *)v12 + 7) & 0x4000) == 0 )
        return 1;
      v13 = 13;
      goto LABEL_13;
    }
    if ( (*((_DWORD *)a4 + 1) & 0x10000) != 0 || (*((_BYTE *)a4 + 4) & 0x40) != 0 )
    {
      if ( v12 == v10 || (*((_DWORD *)v12 + 7) & 0x4000) == 0 )
        return 1;
      v13 = 14;
      goto LABEL_13;
    }
    v25 = a2;
    hMem = 0;
    if ( v12 != v10 && (*((_DWORD *)v12 + 7) & 0x4000) != 0 )
    {
      v17 = CSidString::Get((CSidString *)&v25);
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_37cedf518d6f395f1417435d625f7a12_Traceguids, v17);
    }
    Token = 0;
    if ( (int)CComTemporaryRevertToSelf::RevertToSelf((CComTemporaryRevertToSelf *)&Token) >= 0 )
    {
      LODWORD(v28) = 0;
      v22 = 0;
      v23 = 0;
      v27 = 0;
      if ( (int)CscLib_QueryUserPrincipalID(a2, &v27) >= 0
        && (int)CscLib_QueryAccessInformationForPrincipal(SourceString, v27, (unsigned int *)&v28, &v23, &v22) >= 0 )
      {
        v18 = WPP_GLOBAL_Control;
        v19 = (int)v28;
        v20 = v22;
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0 )
        {
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            WPP_37cedf518d6f395f1417435d625f7a12_Traceguids,
            (unsigned int)v28,
            v22);
          v18 = WPP_GLOBAL_Control;
        }
        if ( v19 && !v20 )
        {
          if ( v18 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_DWORD *)v18 + 7) & 0x4000) != 0 )
            WPP_SF_S(*((_QWORD *)v18 + 2), 17, WPP_37cedf518d6f395f1417435d625f7a12_Traceguids, SourceString);
          if ( Token )
          {
            if ( !SetThreadToken(0, Token) )
              ResultFromLastError();
            CloseHandle(Token);
            Token = 0;
          }
          LocalFree(hMem);
          return 1;
        }
      }
    }
    if ( Token )
    {
      if ( !SetThreadToken(0, Token) )
        ResultFromLastError();
      CloseHandle(Token);
      Token = 0;
    }
    LocalFree(hMem);
    v12 = WPP_GLOBAL_Control;
  }
LABEL_59:
  if ( v12 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x4000) != 0 )
    WPP_SF_S(*((_QWORD *)v12 + 2), 19, WPP_37cedf518d6f395f1417435d625f7a12_Traceguids, SourceString);
  return 0;
}

```

## disassembly

```asm
0x18004aa6c  mov     [rsp-38h+arg_0], rbx
0x18004aa71  push    rbp
0x18004aa72  push    rsi
0x18004aa73  push    rdi
0x18004aa74  push    r12
0x18004aa76  push    r13
0x18004aa78  push    r14
0x18004aa7a  push    r15
0x18004aa7c  mov     rbp, rsp
0x18004aa7f  sub     rsp, 50h
0x18004aa83  mov     rsi, r9
0x18004aa86  mov     r14d, r8d
0x18004aa89  mov     r15, rdx
0x18004aa8c  mov     rbx, rcx
0x18004aa8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004aa96  lea     r10, WPP_GLOBAL_Control
0x18004aa9d  cmp     rcx, r10
0x18004aaa0  jz      short loc_18004AAC8
0x18004aaa2  test    dword ptr [rcx+1Ch], 4000h
0x18004aaa9  jz      short loc_18004AAC8
0x18004aaab  mov     rcx, [rcx+10h]
0x18004aaaf  mov     r9, rbx
0x18004aab2  mov     [rsp+50h+var_28], r8d
0x18004aab7  mov     [rsp+50h+var_30], rdx
0x18004aabc  call    WPP_SF_SqD
0x18004aac1  lea     r10, WPP_GLOBAL_Control
0x18004aac8  mov     r12d, r14d
0x18004aacb  mov     [rbp+arg_18], rsi
0x18004aacf  and     r12d, 2
0x18004aad3  lea     rcx, [rbp+arg_18]; this
0x18004aad7  mov     edi, r14d
0x18004aada  mov     r9d, 0
0x18004aae0  setz    r9b
0x18004aae4  not     edi
0x18004aae6  and     edi, 1
0x18004aae9  call    ?IsItemPinned@CCacheItemInfo@@QEBAHXZ; CCacheItemInfo::IsItemPinned(void)
0x18004aaee  mov     r13d, eax
0x18004aaf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004aaf8  cmp     rcx, r10
0x18004aafb  jz      short loc_18004AB31
0x18004aafd  test    dword ptr [rcx+1Ch], 4000h
0x18004ab04  jz      short loc_18004AB31
0x18004ab06  mov     rcx, [rcx+10h]
0x18004ab0a  lea     r8, WPP_37cedf518d6f395f1417435d625f7a12_Traceguids
0x18004ab11  mov     [rsp+50h+var_28], eax
0x18004ab15  mov     edx, 0Bh
0x18004ab1a  mov     dword ptr [rsp+50h+var_30], edi
0x18004ab1e  call    WPP_SF_DDD
0x18004ab23  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ab2a  lea     r10, WPP_GLOBAL_Control
0x18004ab31  test    r13d, r13d
0x18004ab34  jz      short loc_18004AB7E
0x18004ab36  xor     r13d, r13d
0x18004ab39  test    r12d, r12d
0x18004ab3c  jz      short loc_18004AB85
0x18004ab3e  test    dword ptr [rsi+4], 800000h
0x18004ab45  jz      loc_18004ADEA
0x18004ab4b  cmp     rcx, r10
0x18004ab4e  jz      loc_18004AD89
0x18004ab54  test    dword ptr [rcx+1Ch], 4000h
0x18004ab5b  jz      loc_18004AD89
0x18004ab61  mov     edx, 12h
0x18004ab66  mov     rcx, [rcx+10h]
0x18004ab6a  lea     r8, WPP_37cedf518d6f395f1417435d625f7a12_Traceguids
0x18004ab71  mov     r9, rbx
0x18004ab74  call    WPP_SF_S
0x18004ab79  jmp     loc_18004AD89
0x18004ab7e  xor     r13d, r13d
0x18004ab81  test    edi, edi
0x18004ab83  jz      short loc_18004AB3E
0x18004ab85  test    byte ptr [rsi+4], 1
0x18004ab89  jnz     short loc_18004AB9D
0x18004ab8b  test    byte ptr [rsi+4], 10h
0x18004ab8f  jnz     short loc_18004AB9D
0x18004ab91  test    dword ptr [rsi+4], 400h
0x18004ab98  mov     edi, r13d
0x18004ab9b  jz      short loc_18004ABA2
0x18004ab9d  mov     edi, 1
0x18004aba2  mov     r12d, [rsi+78h]
0x18004aba6  and     r14d, 4
0x18004abaa  mov     eax, r13d
0x18004abad  mov     r9d, r13d
0x18004abb0  setnz   al
0x18004abb3  and     r12d, 6
0x18004abb7  cmp     r12d, 6
0x18004abbb  setz    r9b
0x18004abbf  mov     r8d, 4000h
0x18004abc5  cmp     rcx, r10
0x18004abc8  jz      short loc_18004AC01
0x18004abca  test    [rcx+1Ch], r8d
0x18004abce  jz      short loc_18004AC01
0x18004abd0  mov     rcx, [rcx+10h]
0x18004abd4  lea     r8, WPP_37cedf518d6f395f1417435d625f7a12_Traceguids
0x18004abdb  mov     [rsp+50h+var_28], eax
0x18004abdf  mov     edx, 0Ch
0x18004abe4  mov     dword ptr [rsp+50h+var_30], edi
0x18004abe8  call    WPP_SF_DDD
0x18004abed  mov     rcx, cs:WPP_GLOBAL_Control
0x18004abf4  lea     r10, WPP_GLOBAL_Control
0x18004abfb  mov     r8d, 4000h
0x18004ac01  test    edi, edi
0x18004ac03  jz      short loc_18004AC14
0x18004ac05  test    r14d, r14d
0x18004ac08  jnz     short loc_18004AC14
0x18004ac0a  cmp     r12d, 6
0x18004ac0e  jnz     loc_18004ADEA
0x18004ac14  test    r15, r15
0x18004ac17  jnz     short loc_18004AC35
0x18004ac19  cmp     rcx, r10
0x18004ac1c  jz      loc_18004AD89
0x18004ac22  test    [rcx+1Ch], r8d
0x18004ac26  jz      loc_18004AD89
0x18004ac2c  lea     edx, [r15+0Dh]
0x18004ac30  jmp     loc_18004AB66
0x18004ac35  test    dword ptr [rsi+4], 10000h
0x18004ac3c  jnz     loc_18004ADD5
0x18004ac42  test    byte ptr [rsi+4], 40h
0x18004ac46  jnz     loc_18004ADD5
0x18004ac4c  mov     [rbp+var_10], r15
0x18004ac50  mov     [rbp+hMem], r13
0x18004ac54  cmp     rcx, r10
0x18004ac57  jz      short loc_18004AC87
0x18004ac59  test    [rcx+1Ch], r8d
0x18004ac5d  jz      short loc_18004AC87
0x18004ac5f  lea     rcx, [rbp+var_10]; this
0x18004ac63  call    ?Get@CSidString@@QEBAPEBGXZ; CSidString::Get(void)
0x18004ac68  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ac6f  lea     r8, WPP_37cedf518d6f395f1417435d625f7a12_Traceguids
0x18004ac76  mov     edx, 0Fh
0x18004ac7b  mov     r9, rax
0x18004ac7e  mov     rcx, [rcx+10h]
0x18004ac82  call    WPP_SF_S
0x18004ac87  lea     rcx, [rbp+Token]; this
0x18004ac8b  mov     [rbp+Token], r13
0x18004ac8f  call    ?RevertToSelf@CComTemporaryRevertToSelf@@QEAAJXZ; CComTemporaryRevertToSelf::RevertToSelf(void)
0x18004ac94  test    eax, eax
0x18004ac96  js      loc_18004AD93
0x18004ac9c  lea     rdx, [rbp+arg_10]; unsigned __int16 *
0x18004aca0  mov     dword ptr [rbp+arg_18], r13d
0x18004aca4  mov     rcx, r15; void *
0x18004aca7  mov     [rbp+var_20], r13d
0x18004acab  mov     [rbp+var_1C], r13d
0x18004acaf  mov     [rbp+arg_10], r13w
0x18004acb4  call    ?CscLib_QueryUserPrincipalID@@YAJPEAXPEAG@Z; CscLib_QueryUserPrincipalID(void *,ushort *)
0x18004acb9  test    eax, eax
0x18004acbb  js      loc_18004AD93
0x18004acc1  movzx   edx, [rbp+arg_10]; unsigned __int16
0x18004acc5  lea     rax, [rbp+var_20]
0x18004acc9  lea     r9, [rbp+var_1C]; unsigned int *
0x18004accd  mov     [rsp+50h+var_30], rax; unsigned int *
0x18004acd2  lea     r8, [rbp+arg_18]; unsigned int *
0x18004acd6  mov     rcx, rbx; SourceString
0x18004acd9  call    ?CscLib_QueryAccessInformationForPrincipal@@YAJPEBGGPEAK11@Z; CscLib_QueryAccessInformationForPrincipal(ushort const *,ushort,ulong *,ulong *,ulong *)
0x18004acde  test    eax, eax
0x18004ace0  js      loc_18004AD93
0x18004ace6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004aced  lea     r14, WPP_GLOBAL_Control
0x18004acf4  mov     edi, dword ptr [rbp+arg_18]
0x18004acf7  mov     esi, [rbp+var_20]
0x18004acfa  cmp     rcx, r14
0x18004acfd  jz      short loc_18004AD2B
0x18004acff  test    dword ptr [rcx+1Ch], 4000h
0x18004ad06  jz      short loc_18004AD2B
0x18004ad08  mov     rcx, [rcx+10h]
0x18004ad0c  lea     r8, WPP_37cedf518d6f395f1417435d625f7a12_Traceguids
0x18004ad13  mov     edx, 10h
0x18004ad18  mov     dword ptr [rsp+50h+var_30], esi
0x18004ad1c  mov     r9d, edi
0x18004ad1f  call    WPP_SF_dd
0x18004ad24  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ad2b  test    edi, edi
0x18004ad2d  jz      short loc_18004AD9A
0x18004ad2f  test    esi, esi
0x18004ad31  jnz     short loc_18004AD9A
0x18004ad33  cmp     rcx, r14
0x18004ad36  jz      short loc_18004AD57
0x18004ad38  test    dword ptr [rcx+1Ch], 4000h
0x18004ad3f  jz      short loc_18004AD57
0x18004ad41  mov     rcx, [rcx+10h]
0x18004ad45  lea     edx, [rsi+11h]
0x18004ad48  mov     r9, rbx
0x18004ad4b  lea     r8, WPP_37cedf518d6f395f1417435d625f7a12_Traceguids
0x18004ad52  call    WPP_SF_S
0x18004ad57  mov     rdx, [rbp+Token]; Token
0x18004ad5b  test    rdx, rdx
0x18004ad5e  jz      short loc_18004AD7F
0x18004ad60  xor     ecx, ecx; Thread
0x18004ad62  call    cs:__imp_SetThreadToken
0x18004ad68  test    eax, eax
0x18004ad6a  jnz     short loc_18004AD71
0x18004ad6c  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18004ad71  mov     rcx, [rbp+Token]; hObject
0x18004ad75  call    cs:__imp_CloseHandle
0x18004ad7b  mov     [rbp+Token], r13
0x18004ad7f  mov     rcx, [rbp+hMem]; hMem
0x18004ad83  call    cs:__imp_LocalFree
0x18004ad89  mov     eax, 1
0x18004ad8e  jmp     loc_18004AE19
0x18004ad93  lea     r14, WPP_GLOBAL_Control
0x18004ad9a  mov     rdx, [rbp+Token]; Token
0x18004ad9e  test    rdx, rdx
0x18004ada1  jz      short loc_18004ADC2
0x18004ada3  xor     ecx, ecx; Thread
0x18004ada5  call    cs:__imp_SetThreadToken
0x18004adab  test    eax, eax
0x18004adad  jnz     short loc_18004ADB4
0x18004adaf  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18004adb4  mov     rcx, [rbp+Token]; hObject
0x18004adb8  call    cs:__imp_CloseHandle
0x18004adbe  mov     [rbp+Token], r13
0x18004adc2  mov     rcx, [rbp+hMem]; hMem
0x18004adc6  call    cs:__imp_LocalFree
0x18004adcc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004add3  jmp     short loc_18004ADF1
0x18004add5  cmp     rcx, r10
0x18004add8  jz      short loc_18004AD89
0x18004adda  test    [rcx+1Ch], r8d
0x18004adde  jz      short loc_18004AD89
0x18004ade0  mov     edx, 0Eh
0x18004ade5  jmp     loc_18004AB66
0x18004adea  lea     r14, WPP_GLOBAL_Control
0x18004adf1  cmp     rcx, r14
0x18004adf4  jz      short loc_18004AE17
0x18004adf6  test    dword ptr [rcx+1Ch], 4000h
0x18004adfd  jz      short loc_18004AE17
0x18004adff  mov     rcx, [rcx+10h]
0x18004ae03  lea     r8, WPP_37cedf518d6f395f1417435d625f7a12_Traceguids
0x18004ae0a  mov     edx, 13h
0x18004ae0f  mov     r9, rbx
0x18004ae12  call    WPP_SF_S
0x18004ae17  xor     eax, eax
0x18004ae19  mov     rbx, [rsp+50h+arg_0]
0x18004ae21  add     rsp, 50h
0x18004ae25  pop     r15
0x18004ae27  pop     r14
0x18004ae29  pop     r13
0x18004ae2b  pop     r12
0x18004ae2d  pop     rdi
0x18004ae2e  pop     rsi
0x18004ae2f  pop     rbp
0x18004ae30  retn
```
