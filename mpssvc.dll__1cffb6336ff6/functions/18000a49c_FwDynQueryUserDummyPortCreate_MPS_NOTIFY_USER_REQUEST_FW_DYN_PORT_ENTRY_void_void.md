# FwDynQueryUserDummyPortCreate(_MPS_NOTIFY_USER_REQUEST *,FW_DYN_PORT_ENTRY_ * *,void * *,void * *)

- ea: `0x18000a49c`
- end: `0x18000a6d1`
- name: `?FwDynQueryUserDummyPortCreate@@YAJPEAU_MPS_NOTIFY_USER_REQUEST@@PEAPEAUFW_DYN_PORT_ENTRY_@@PEAPEAX2@Z`
- size: `565`
- prototype: `__int64 __fastcall(struct _MPS_NOTIFY_USER_REQUEST *, struct FW_DYN_PORT_ENTRY_ **, void **, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800097b0`

## callees

- `0x18000a49c`
- `0x180017110`
- `0x1800356ec`
- `0x18004afe4`
- `0x18006f520`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a514`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a514`
- `fwbase!FwGetLongPathName` at `0x18000a594`
- `fwbase!FwGetLongPathName` at `0x18000a594`
- `fwbase!FwCloseHandle` at `0x18000a6a4`
- `fwbase!FwCloseHandle` at `0x18000a6ad`
- `fwbase!FwCloseHandle` at `0x18000a6a4`
- `fwbase!FwCloseHandle` at `0x18000a6ad`
- `fwbase!FwSubstituteDeviceName` at `0x18000a61e`
- `fwbase!FwSubstituteDeviceName` at `0x18000a61e`
- `fwbase!FwStringCopy` at `0x18000a529`
- `fwbase!FwStringCopy` at `0x18000a529`
- `fwbase!FwReportReturnError` at `0x18000a560`
- `fwbase!FwReportReturnError` at `0x18000a6c4`
- `fwbase!FwReportReturnError` at `0x18000a560`
- `fwbase!FwReportReturnError` at `0x18000a6c4`
- `fwbase!FwAlloc` at `0x18000a4e9`
- `fwbase!FwAlloc` at `0x18000a4e9`
- `fwbase!FwFree` at `0x18000a5e8`
- `fwbase!FwFree` at `0x18000a5e8`
- `fwbase!FwReportErrorAsWinError` at `0x18000a649`
- `fwbase!FwReportErrorAsWinError` at `0x18000a649`

## string_xrefs

- `0x18000a559`: `FwDynQueryUserDummyPortCreate`
- `0x18000a642`: `FwDynQueryUserDummyPortCreate`
- `0x18000a6bd`: `FwDynQueryUserDummyPortCreate`

## pseudocode

```c
__int64 __fastcall FwDynQueryUserDummyPortCreate(
        struct _MPS_NOTIFY_USER_REQUEST *a1,
        struct FW_DYN_PORT_ENTRY_ **a2,
        void **a3,
        void **a4)
{
  void *v8; // r12
  void *v9; // r13
  __int64 v10; // rdi
  __int64 v11; // r8
  int LongPathName; // eax
  int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned __int16 *v19; // [rsp+20h] [rbp-68h] BYREF
  int v20; // [rsp+28h] [rbp-60h] BYREF

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v8 = (void *)*((_QWORD *)a1 + 11);
  v9 = (void *)*((_QWORD *)a1 + 10);
  v19 = 0;
  v20 = 0;
  v10 = FwAlloc(152);
  if ( v10 )
  {
    *(_DWORD *)(v10 + 24) = *((_DWORD *)a1 + 6);
    if ( a1 == (struct _MPS_NOTIFY_USER_REQUEST *)-104LL )
    {
      v14 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        goto LABEL_7;
      v17 = 25;
    }
    else
    {
      if ( !lstrcmpiW(L"System", (LPCWSTR)a1 + 52) )
      {
        LongPathName = FwStringCopy(L"System", v10 + 32);
        v13 = LongPathName;
        if ( LongPathName >= 0 )
          goto LABEL_13;
        goto LABEL_20;
      }
      if ( (int)ConvertFilePath((unsigned __int16 *)a1 + 52, &v19) < 0 )
      {
        LongPathName = FwSubstituteDeviceName((char *)a1 + 104, &v19);
        v13 = LongPathName;
        if ( LongPathName < 0 )
        {
LABEL_20:
          v15 = (unsigned int)LongPathName;
          goto LABEL_8;
        }
      }
      if ( v19 )
      {
        LongPathName = FwGetLongPathName(v19, v10 + 32, &v20);
        v13 = LongPathName;
        if ( LongPathName < 0 )
          goto LABEL_20;
        if ( v20 )
        {
LABEL_13:
          *(_DWORD *)(v10 + 40) = (*((_BYTE *)a1 + 72) & 0x60) != 0;
          *(_DWORD *)(v10 + 44) = (*((_DWORD *)a1 + 18) >> 1) & 1;
          *(_WORD *)(v10 + 48) = *((_WORD *)a1 + 33);
          *(_DWORD *)(v10 + 52) = *((unsigned __int8 *)a1 + 68);
          *a2 = (struct FW_DYN_PORT_ENTRY_ *)v10;
          *a3 = v8;
          *a4 = v9;
          goto LABEL_14;
        }
LABEL_7:
        v15 = 2147500037LL;
        v13 = -2147467259;
LABEL_8:
        FwReportReturnError("FwDynQueryUserDummyPortCreate", v15, v11);
        goto LABEL_14;
      }
      v14 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        goto LABEL_7;
      v17 = 26;
    }
    WPP_SF_(*(_QWORD *)(v14 + 16), v17, WPP_98cae50d156a33be091d6122a49fdb37_Traceguids);
    goto LABEL_7;
  }
  v13 = FwReportErrorAsWinError("FwDynQueryUserDummyPortCreate", "FwAlloc", 8);
LABEL_14:
  if ( v19 )
    FwFree(v19);
  if ( v13 < 0 )
  {
    FwCloseHandle(v9);
    FwCloseHandle(v8);
    FwDynPortDestroy((struct FW_DYN_PORT_ENTRY_ *)v10);
    return (unsigned int)FwReportReturnError("FwDynQueryUserDummyPortCreate", (unsigned int)v13, v18);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000a49c  push    rbx
0x18000a49e  push    rbp
0x18000a49f  push    rsi
0x18000a4a0  push    rdi
0x18000a4a1  push    r12
0x18000a4a3  push    r13
0x18000a4a5  push    r14
0x18000a4a7  push    r15
0x18000a4a9  sub     rsp, 48h
0x18000a4ad  mov     rax, cs:__security_cookie
0x18000a4b4  xor     rax, rsp
0x18000a4b7  mov     [rsp+88h+var_58], rax
0x18000a4bc  xor     ebx, ebx
0x18000a4be  mov     rsi, rcx
0x18000a4c1  mov     [rdx], rbx
0x18000a4c4  mov     rbp, r9
0x18000a4c7  mov     [r8], rbx
0x18000a4ca  mov     r15, r8
0x18000a4cd  mov     [r9], rbx
0x18000a4d0  mov     r14, rdx
0x18000a4d3  mov     r12, [rcx+58h]
0x18000a4d7  mov     r13, [rcx+50h]
0x18000a4db  mov     ecx, 98h
0x18000a4e0  mov     [rsp+88h+var_68], rbx
0x18000a4e5  mov     [rsp+88h+var_60], ebx
0x18000a4e9  call    cs:__imp_FwAlloc
0x18000a4ef  mov     rdi, rax
0x18000a4f2  test    rax, rax
0x18000a4f5  jz      loc_18000A635
0x18000a4fb  mov     eax, [rsi+18h]
0x18000a4fe  lea     rbx, [rsi+68h]
0x18000a502  mov     [rdi+18h], eax
0x18000a505  test    rbx, rbx
0x18000a508  jz      short loc_18000A53B
0x18000a50a  mov     rdx, rbx; lpString2
0x18000a50d  lea     rcx, aSystem_0; "System"
0x18000a514  call    cs:__imp_lstrcmpiW
0x18000a51a  test    eax, eax
0x18000a51c  jnz     short loc_18000A568
0x18000a51e  lea     rdx, [rdi+20h]
0x18000a522  lea     rcx, aSystem_0; "System"
0x18000a529  call    cs:__imp_FwStringCopy
0x18000a52f  mov     ebx, eax
0x18000a531  test    eax, eax
0x18000a533  js      loc_18000A62E
0x18000a539  jmp     short loc_18000A5AB
0x18000a53b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a542  lea     rax, WPP_GLOBAL_Control
0x18000a549  cmp     rcx, rax
0x18000a54c  jnz     loc_18000A653
0x18000a552  mov     edx, 80004005h
0x18000a557  mov     ebx, edx
0x18000a559  lea     rcx, aFwdynqueryuser; "FwDynQueryUserDummyPortCreate"
0x18000a560  call    cs:__imp_FwReportReturnError
0x18000a566  jmp     short loc_18000A5DE
0x18000a568  lea     rdx, [rsp+88h+var_68]; unsigned __int16 **
0x18000a56d  mov     rcx, rbx; unsigned __int16 *
0x18000a570  call    ?ConvertFilePath@@YAJPEAGPEAPEAG@Z; ConvertFilePath(ushort *,ushort * *)
0x18000a575  test    eax, eax
0x18000a577  js      loc_18000A616
0x18000a57d  mov     rcx, [rsp+88h+var_68]
0x18000a582  test    rcx, rcx
0x18000a585  jz      loc_18000A67E
0x18000a58b  lea     rdx, [rdi+20h]
0x18000a58f  lea     r8, [rsp+88h+var_60]
0x18000a594  call    cs:__imp_FwGetLongPathName
0x18000a59a  mov     ebx, eax
0x18000a59c  test    eax, eax
0x18000a59e  js      loc_18000A62E
0x18000a5a4  cmp     [rsp+88h+var_60], 0
0x18000a5a9  jz      short loc_18000A552
0x18000a5ab  test    byte ptr [rsi+48h], 60h
0x18000a5af  mov     eax, 0
0x18000a5b4  setnz   al
0x18000a5b7  mov     [rdi+28h], eax
0x18000a5ba  mov     eax, [rsi+48h]
0x18000a5bd  shr     eax, 1
0x18000a5bf  and     eax, 1
0x18000a5c2  mov     [rdi+2Ch], eax
0x18000a5c5  movzx   eax, word ptr [rsi+42h]
0x18000a5c9  mov     [rdi+30h], ax
0x18000a5cd  movzx   eax, byte ptr [rsi+44h]
0x18000a5d1  mov     [rdi+34h], eax
0x18000a5d4  mov     [r14], rdi
0x18000a5d7  mov     [r15], r12
0x18000a5da  mov     [rbp+0], r13
0x18000a5de  mov     rcx, [rsp+88h+var_68]
0x18000a5e3  test    rcx, rcx
0x18000a5e6  jz      short loc_18000A5EE
0x18000a5e8  call    cs:__imp_FwFree
0x18000a5ee  test    ebx, ebx
0x18000a5f0  js      loc_18000A6A1
0x18000a5f6  mov     eax, ebx
0x18000a5f8  mov     rcx, [rsp+88h+var_58]
0x18000a5fd  xor     rcx, rsp; StackCookie
0x18000a600  call    __security_check_cookie
0x18000a605  add     rsp, 48h
0x18000a609  pop     r15
0x18000a60b  pop     r14
0x18000a60d  pop     r13
0x18000a60f  pop     r12
0x18000a611  pop     rdi
0x18000a612  pop     rsi
0x18000a613  pop     rbp
0x18000a614  pop     rbx
0x18000a615  retn
0x18000a616  lea     rdx, [rsp+88h+var_68]
0x18000a61b  mov     rcx, rbx
0x18000a61e  call    cs:__imp_FwSubstituteDeviceName
0x18000a624  mov     ebx, eax
0x18000a626  test    eax, eax
0x18000a628  jns     loc_18000A57D
0x18000a62e  mov     edx, eax
0x18000a630  jmp     loc_18000A559
0x18000a635  mov     r8d, 8
0x18000a63b  lea     rdx, aFwalloc_0; "FwAlloc"
0x18000a642  lea     rcx, aFwdynqueryuser; "FwDynQueryUserDummyPortCreate"
0x18000a649  call    cs:__imp_FwReportErrorAsWinError
0x18000a64f  mov     ebx, eax
0x18000a651  jmp     short loc_18000A5DE
0x18000a653  test    byte ptr [rcx+1Ch], 2
0x18000a657  jz      loc_18000A552
0x18000a65d  mov     edx, 19h
0x18000a662  jmp     short loc_18000A669
0x18000a664  mov     edx, 1Ah
0x18000a669  mov     rcx, [rcx+10h]
0x18000a66d  lea     r8, WPP_98cae50d156a33be091d6122a49fdb37_Traceguids
0x18000a674  call    WPP_SF_
0x18000a679  jmp     loc_18000A552
0x18000a67e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a685  lea     rax, WPP_GLOBAL_Control
0x18000a68c  cmp     rcx, rax
0x18000a68f  jz      loc_18000A552
0x18000a695  test    byte ptr [rcx+1Ch], 2
0x18000a699  jz      loc_18000A552
0x18000a69f  jmp     short loc_18000A664
0x18000a6a1  mov     rcx, r13
0x18000a6a4  call    cs:__imp_FwCloseHandle
0x18000a6aa  mov     rcx, r12
0x18000a6ad  call    cs:__imp_FwCloseHandle
0x18000a6b3  mov     rcx, rdi; struct FW_DYN_PORT_ENTRY_ *
0x18000a6b6  call    ?FwDynPortDestroy@@YAXPEAUFW_DYN_PORT_ENTRY_@@@Z; FwDynPortDestroy(FW_DYN_PORT_ENTRY_ *)
0x18000a6bb  mov     edx, ebx
0x18000a6bd  lea     rcx, aFwdynqueryuser; "FwDynQueryUserDummyPortCreate"
0x18000a6c4  call    cs:__imp_FwReportReturnError
0x18000a6ca  mov     ebx, eax
0x18000a6cc  jmp     loc_18000A5F6
```
