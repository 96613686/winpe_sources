# FwDynQueryUserDummyPortCreate(_MPS_NOTIFY_USER_REQUEST *,FW_DYN_PORT_ENTRY_ * *,void * *,void * *)

- ea: `0x180009bc4`
- end: `0x180009e3f`
- name: `?FwDynQueryUserDummyPortCreate@@YAJPEAU_MPS_NOTIFY_USER_REQUEST@@PEAPEAUFW_DYN_PORT_ENTRY_@@PEAPEAX2@Z`
- size: `635`
- prototype: `__int64 __fastcall(struct _MPS_NOTIFY_USER_REQUEST *, struct FW_DYN_PORT_ENTRY_ **, void **, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180008e00`

## callees

- `0x180009bc4`
- `0x1800192e0`
- `0x180033ebc`
- `0x18004cd94`
- `0x1800729c0`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009c42`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009c42`
- `fwbase!FwReportErrorAsWinError` at `0x180009d9c`
- `fwbase!FwReportErrorAsWinError` at `0x180009d9c`
- `fwbase!FwGetLongPathName` at `0x180009cd4`
- `fwbase!FwGetLongPathName` at `0x180009cd4`
- `fwbase!FwCloseHandle` at `0x180009e00`
- `fwbase!FwCloseHandle` at `0x180009e0f`
- `fwbase!FwCloseHandle` at `0x180009e00`
- `fwbase!FwCloseHandle` at `0x180009e0f`
- `fwbase!FwSubstituteDeviceName` at `0x180009d6b`
- `fwbase!FwSubstituteDeviceName` at `0x180009d6b`
- `fwbase!FwStringCopy` at `0x180009c5d`
- `fwbase!FwStringCopy` at `0x180009c5d`
- `fwbase!FwReportReturnError` at `0x180009c9a`
- `fwbase!FwReportReturnError` at `0x180009e2c`
- `fwbase!FwReportReturnError` at `0x180009c9a`
- `fwbase!FwReportReturnError` at `0x180009e2c`
- `fwbase!FwAlloc` at `0x180009c11`
- `fwbase!FwAlloc` at `0x180009c11`
- `fwbase!FwFree` at `0x180009d2e`
- `fwbase!FwFree` at `0x180009d2e`

## string_xrefs

- `0x180009c93`: `FwDynQueryUserDummyPortCreate`
- `0x180009d95`: `FwDynQueryUserDummyPortCreate`
- `0x180009e25`: `FwDynQueryUserDummyPortCreate`

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
  int LongPathName; // eax
  int v12; // ebx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v16; // rdx
  unsigned __int16 *v17; // [rsp+20h] [rbp-68h] BYREF
  int v18; // [rsp+28h] [rbp-60h] BYREF

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v8 = (void *)*((_QWORD *)a1 + 11);
  v9 = (void *)*((_QWORD *)a1 + 10);
  v17 = 0;
  v18 = 0;
  v10 = FwAlloc(152);
  if ( v10 )
  {
    *(_DWORD *)(v10 + 24) = *((_DWORD *)a1 + 6);
    if ( a1 == (struct _MPS_NOTIFY_USER_REQUEST *)-104LL )
    {
      v13 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        goto LABEL_7;
      v16 = 25;
    }
    else
    {
      if ( !lstrcmpiW(L"System", (LPCWSTR)a1 + 52) )
      {
        LongPathName = FwStringCopy(L"System", v10 + 32);
        v12 = LongPathName;
        if ( LongPathName >= 0 )
          goto LABEL_13;
        goto LABEL_20;
      }
      if ( (int)ConvertFilePath((unsigned __int16 *)a1 + 52, &v17) < 0 )
      {
        LongPathName = FwSubstituteDeviceName((char *)a1 + 104, &v17);
        v12 = LongPathName;
        if ( LongPathName < 0 )
        {
LABEL_20:
          v14 = (unsigned int)LongPathName;
          goto LABEL_8;
        }
      }
      if ( v17 )
      {
        LongPathName = FwGetLongPathName(v17, v10 + 32, &v18);
        v12 = LongPathName;
        if ( LongPathName < 0 )
          goto LABEL_20;
        if ( v18 )
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
        v14 = 2147500037LL;
        v12 = -2147467259;
LABEL_8:
        FwReportReturnError("FwDynQueryUserDummyPortCreate", v14);
        goto LABEL_14;
      }
      v13 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        goto LABEL_7;
      v16 = 26;
    }
    WPP_SF_(*(_QWORD *)(v13 + 16), v16, WPP_98cae50d156a33be091d6122a49fdb37_Traceguids);
    goto LABEL_7;
  }
  v12 = FwReportErrorAsWinError("FwDynQueryUserDummyPortCreate", "FwAlloc", 8);
LABEL_14:
  if ( v17 )
    FwFree(v17);
  if ( v12 < 0 )
  {
    FwCloseHandle(v9);
    FwCloseHandle(v8);
    FwDynPortDestroy((struct FW_DYN_PORT_ENTRY_ *)v10);
    return (unsigned int)FwReportReturnError("FwDynQueryUserDummyPortCreate", (unsigned int)v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180009bc4  push    rbx
0x180009bc6  push    rbp
0x180009bc7  push    rsi
0x180009bc8  push    rdi
0x180009bc9  push    r12
0x180009bcb  push    r13
0x180009bcd  push    r14
0x180009bcf  push    r15
0x180009bd1  sub     rsp, 48h
0x180009bd5  mov     rax, cs:__security_cookie
0x180009bdc  xor     rax, rsp
0x180009bdf  mov     [rsp+88h+var_58], rax
0x180009be4  xor     ebx, ebx
0x180009be6  mov     rsi, rcx
0x180009be9  mov     [rdx], rbx
0x180009bec  mov     rbp, r9
0x180009bef  mov     [r8], rbx
0x180009bf2  mov     r15, r8
0x180009bf5  mov     [r9], rbx
0x180009bf8  mov     r14, rdx
0x180009bfb  mov     r12, [rcx+58h]
0x180009bff  mov     r13, [rcx+50h]
0x180009c03  mov     ecx, 98h
0x180009c08  mov     [rsp+88h+var_68], rbx
0x180009c0d  mov     [rsp+88h+var_60], ebx
0x180009c11  call    cs:__imp_FwAlloc
0x180009c18  nop     dword ptr [rax+rax+00h]
0x180009c1d  mov     rdi, rax
0x180009c20  test    rax, rax
0x180009c23  jz      loc_180009D88
0x180009c29  mov     eax, [rsi+18h]
0x180009c2c  lea     rbx, [rsi+68h]
0x180009c30  mov     [rdi+18h], eax
0x180009c33  test    rbx, rbx
0x180009c36  jz      short loc_180009C75
0x180009c38  mov     rdx, rbx; lpString2
0x180009c3b  lea     rcx, aSystem_0; "System"
0x180009c42  call    cs:__imp_lstrcmpiW
0x180009c49  nop     dword ptr [rax+rax+00h]
0x180009c4e  test    eax, eax
0x180009c50  jnz     short loc_180009CA8
0x180009c52  lea     rdx, [rdi+20h]
0x180009c56  lea     rcx, aSystem_0; "System"
0x180009c5d  call    cs:__imp_FwStringCopy
0x180009c64  nop     dword ptr [rax+rax+00h]
0x180009c69  mov     ebx, eax
0x180009c6b  test    eax, eax
0x180009c6d  js      loc_180009D81
0x180009c73  jmp     short loc_180009CF1
0x180009c75  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c7c  lea     rax, WPP_GLOBAL_Control
0x180009c83  cmp     rcx, rax
0x180009c86  jnz     loc_180009DAF
0x180009c8c  mov     edx, 80004005h
0x180009c91  mov     ebx, edx
0x180009c93  lea     rcx, aFwdynqueryuser; "FwDynQueryUserDummyPortCreate"
0x180009c9a  call    cs:__imp_FwReportReturnError
0x180009ca1  nop     dword ptr [rax+rax+00h]
0x180009ca6  jmp     short loc_180009D24
0x180009ca8  lea     rdx, [rsp+88h+var_68]; unsigned __int16 **
0x180009cad  mov     rcx, rbx; unsigned __int16 *
0x180009cb0  call    ?ConvertFilePath@@YAJPEAGPEAPEAG@Z; ConvertFilePath(ushort *,ushort * *)
0x180009cb5  test    eax, eax
0x180009cb7  js      loc_180009D63
0x180009cbd  mov     rcx, [rsp+88h+var_68]
0x180009cc2  test    rcx, rcx
0x180009cc5  jz      loc_180009DDA
0x180009ccb  lea     rdx, [rdi+20h]
0x180009ccf  lea     r8, [rsp+88h+var_60]
0x180009cd4  call    cs:__imp_FwGetLongPathName
0x180009cdb  nop     dword ptr [rax+rax+00h]
0x180009ce0  mov     ebx, eax
0x180009ce2  test    eax, eax
0x180009ce4  js      loc_180009D81
0x180009cea  cmp     [rsp+88h+var_60], 0
0x180009cef  jz      short loc_180009C8C
0x180009cf1  test    byte ptr [rsi+48h], 60h
0x180009cf5  mov     eax, 0
0x180009cfa  setnz   al
0x180009cfd  mov     [rdi+28h], eax
0x180009d00  mov     eax, [rsi+48h]
0x180009d03  shr     eax, 1
0x180009d05  and     eax, 1
0x180009d08  mov     [rdi+2Ch], eax
0x180009d0b  movzx   eax, word ptr [rsi+42h]
0x180009d0f  mov     [rdi+30h], ax
0x180009d13  movzx   eax, byte ptr [rsi+44h]
0x180009d17  mov     [rdi+34h], eax
0x180009d1a  mov     [r14], rdi
0x180009d1d  mov     [r15], r12
0x180009d20  mov     [rbp+0], r13
0x180009d24  mov     rcx, [rsp+88h+var_68]
0x180009d29  test    rcx, rcx
0x180009d2c  jz      short loc_180009D3A
0x180009d2e  call    cs:__imp_FwFree
0x180009d35  nop     dword ptr [rax+rax+00h]
0x180009d3a  test    ebx, ebx
0x180009d3c  js      loc_180009DFD
0x180009d42  mov     eax, ebx
0x180009d44  mov     rcx, [rsp+88h+var_58]
0x180009d49  xor     rcx, rsp; StackCookie
0x180009d4c  call    __security_check_cookie
0x180009d51  add     rsp, 48h
0x180009d55  pop     r15
0x180009d57  pop     r14
0x180009d59  pop     r13
0x180009d5b  pop     r12
0x180009d5d  pop     rdi
0x180009d5e  pop     rsi
0x180009d5f  pop     rbp
0x180009d60  pop     rbx
0x180009d61  retn
0x180009d63  lea     rdx, [rsp+88h+var_68]
0x180009d68  mov     rcx, rbx
0x180009d6b  call    cs:__imp_FwSubstituteDeviceName
0x180009d72  nop     dword ptr [rax+rax+00h]
0x180009d77  mov     ebx, eax
0x180009d79  test    eax, eax
0x180009d7b  jns     loc_180009CBD
0x180009d81  mov     edx, eax
0x180009d83  jmp     loc_180009C93
0x180009d88  mov     r8d, 8
0x180009d8e  lea     rdx, aFwalloc_0; "FwAlloc"
0x180009d95  lea     rcx, aFwdynqueryuser; "FwDynQueryUserDummyPortCreate"
0x180009d9c  call    cs:__imp_FwReportErrorAsWinError
0x180009da3  nop     dword ptr [rax+rax+00h]
0x180009da8  mov     ebx, eax
0x180009daa  jmp     loc_180009D24
0x180009daf  test    byte ptr [rcx+1Ch], 2
0x180009db3  jz      loc_180009C8C
0x180009db9  mov     edx, 19h
0x180009dbe  jmp     short loc_180009DC5
0x180009dc0  mov     edx, 1Ah
0x180009dc5  mov     rcx, [rcx+10h]
0x180009dc9  lea     r8, WPP_98cae50d156a33be091d6122a49fdb37_Traceguids
0x180009dd0  call    WPP_SF_
0x180009dd5  jmp     loc_180009C8C
0x180009dda  mov     rcx, cs:WPP_GLOBAL_Control
0x180009de1  lea     rax, WPP_GLOBAL_Control
0x180009de8  cmp     rcx, rax
0x180009deb  jz      loc_180009C8C
0x180009df1  test    byte ptr [rcx+1Ch], 2
0x180009df5  jz      loc_180009C8C
0x180009dfb  jmp     short loc_180009DC0
0x180009dfd  mov     rcx, r13
0x180009e00  call    cs:__imp_FwCloseHandle
0x180009e07  nop     dword ptr [rax+rax+00h]
0x180009e0c  mov     rcx, r12
0x180009e0f  call    cs:__imp_FwCloseHandle
0x180009e16  nop     dword ptr [rax+rax+00h]
0x180009e1b  mov     rcx, rdi; struct FW_DYN_PORT_ENTRY_ *
0x180009e1e  call    ?FwDynPortDestroy@@YAXPEAUFW_DYN_PORT_ENTRY_@@@Z; FwDynPortDestroy(FW_DYN_PORT_ENTRY_ *)
0x180009e23  mov     edx, ebx
0x180009e25  lea     rcx, aFwdynqueryuser; "FwDynQueryUserDummyPortCreate"
0x180009e2c  call    cs:__imp_FwReportReturnError
0x180009e33  nop     dword ptr [rax+rax+00h]
0x180009e38  mov     ebx, eax
0x180009e3a  jmp     loc_180009D42
```
