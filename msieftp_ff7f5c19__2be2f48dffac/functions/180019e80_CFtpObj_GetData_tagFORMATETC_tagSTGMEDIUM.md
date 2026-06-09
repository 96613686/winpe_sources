# CFtpObj::GetData(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x180019e80`
- end: `0x180019f9c`
- name: `?GetData@CFtpObj@@UEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `284`
- prototype: `__int64 __fastcall(CFtpObj *__hidden this, struct tagFORMATETC *, STGMEDIUM *pstgmedDest)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180002240`
- `0x180002b60`
- `0x180019e80`
- `0x18001ae3c`
- `0x18001aec8`
- `0x18001af28`
- `0x18001b1b8`
- `0x180026c3c`

## import_xrefs

- `urlmon!CopyStgMedium` at `0x180019f1e`
- `urlmon!CopyStgMedium` at `0x180019f1e`

## pseudocode

```c
HRESULT __fastcall CFtpObj::GetData(CFtpObj *this, struct tagFORMATETC *a2, STGMEDIUM *pstgmedDest)
{
  bool v3; // zf
  HRESULT result; // eax
  int Data; // edx
  __int64 v9; // rdi
  const STGMEDIUM *v10; // rcx
  int ExtraDataIndex; // edi
  int v12[4]; // [rsp+20h] [rbp-88h] BYREF
  _BYTE pitem[48]; // [rsp+30h] [rbp-78h] BYREF
  char v14; // [rsp+60h] [rbp-48h] BYREF

  v3 = *((_DWORD *)this + 20) == 2;
  v12[0] = 0;
  if ( !v3 )
    return -2147024875;
  Data = CFtpObj::_FindData(this, a2, v12);
  if ( Data < 0 )
  {
    if ( Data == -2147024875 )
      return -2147024875;
  }
  else
  {
    v9 = v12[0];
    if ( !v12[0] )
      return CFtpObj::_RenderFileContents(this, a2, pstgmedDest);
    if ( *((_DWORD *)this + 6 * v12[0] + 38) )
    {
      result = CFtpObj::_ForceRender(this, v12[0]);
      if ( result < 0 )
        return result;
      v10 = (const STGMEDIUM *)((char *)this + 16 * v9 + 8 * v9 + 152);
      goto LABEL_10;
    }
  }
  ExtraDataIndex = CFtpObj::_FindExtraDataIndex(this, a2);
  if ( ExtraDataIndex != -1 )
  {
    memset_0(pitem, 0, 0x48u);
    DSA_GetItem(*((HDSA *)this + 9), ExtraDataIndex, pitem);
    v10 = (const STGMEDIUM *)&v14;
LABEL_10:
    result = CopyStgMedium(v10, pstgmedDest);
    pstgmedDest->pUnkForRelease = 0;
    return result;
  }
  return -2147467259;
}

```

## disassembly

```asm
0x180019e80  mov     [rsp+arg_18], rbx
0x180019e85  push    rbp
0x180019e86  push    rsi
0x180019e87  push    rdi
0x180019e88  sub     rsp, 90h
0x180019e8f  mov     rax, cs:__security_cookie
0x180019e96  xor     rax, rsp
0x180019e99  mov     [rsp+0A8h+var_28], rax
0x180019ea1  cmp     dword ptr [rcx+50h], 2
0x180019ea5  mov     rbp, r8
0x180019ea8  mov     rsi, rdx
0x180019eab  mov     [rsp+0A8h+var_88], 0
0x180019eb3  mov     rbx, rcx
0x180019eb6  jz      short loc_180019EC2
0x180019eb8  mov     eax, 80070015h
0x180019ebd  jmp     loc_180019F79
0x180019ec2  lea     r8, [rsp+0A8h+var_88]; int *
0x180019ec7  call    ?_FindData@CFtpObj@@IEAAJPEBUtagFORMATETC@@PEAH@Z; CFtpObj::_FindData(tagFORMATETC const *,int *)
0x180019ecc  mov     edx, eax
0x180019ece  test    eax, eax
0x180019ed0  js      short loc_180019F2E
0x180019ed2  movsxd  rdi, [rsp+0A8h+var_88]
0x180019ed7  test    edi, edi
0x180019ed9  jz      short loc_180019EEE
0x180019edb  lea     r9, [rdi+rdi*2]
0x180019edf  cmp     dword ptr [rbx+r9*8+98h], 0
0x180019ee8  jz      short loc_180019F37
0x180019eea  test    edi, edi
0x180019eec  jnz     short loc_180019EFE
0x180019eee  mov     r8, rbp; struct tagSTGMEDIUM *
0x180019ef1  mov     rdx, rsi; struct tagFORMATETC *
0x180019ef4  mov     rcx, rbx; this
0x180019ef7  call    ?_RenderFileContents@CFtpObj@@IEAAJPEBUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z; CFtpObj::_RenderFileContents(tagFORMATETC const *,tagSTGMEDIUM *)
0x180019efc  jmp     short loc_180019F79
0x180019efe  mov     edx, edi; int
0x180019f00  mov     rcx, rbx; this
0x180019f03  call    ?_ForceRender@CFtpObj@@IEAAJH@Z; CFtpObj::_ForceRender(int)
0x180019f08  test    eax, eax
0x180019f0a  js      short loc_180019F79
0x180019f0c  lea     rcx, ds:13h[rdi*2]
0x180019f14  add     rcx, rdi
0x180019f17  lea     rcx, [rbx+rcx*8]; pcstgmedSrc
0x180019f1b  mov     rdx, rbp; pstgmedDest
0x180019f1e  call    cs:__imp_CopyStgMedium
0x180019f24  mov     qword ptr [rbp+10h], 0
0x180019f2c  jmp     short loc_180019F79
0x180019f2e  mov     eax, 80070015h
0x180019f33  cmp     edx, eax
0x180019f35  jz      short loc_180019F77
0x180019f37  mov     rdx, rsi; struct tagFORMATETC *
0x180019f3a  mov     rcx, rbx; this
0x180019f3d  call    ?_FindExtraDataIndex@CFtpObj@@IEAAHPEBUtagFORMATETC@@@Z; CFtpObj::_FindExtraDataIndex(tagFORMATETC const *)
0x180019f42  mov     edi, eax
0x180019f44  cmp     eax, 0FFFFFFFFh
0x180019f47  jnz     short loc_180019F50
0x180019f49  mov     eax, 80004005h
0x180019f4e  jmp     short loc_180019F79
0x180019f50  xor     edx, edx; Val
0x180019f52  lea     rcx, [rsp+0A8h+pitem]; void *
0x180019f57  lea     r8d, [rdx+48h]; Size
0x180019f5b  call    memset_0
0x180019f60  mov     rcx, [rbx+48h]; hdsa
0x180019f64  lea     r8, [rsp+0A8h+pitem]; pitem
0x180019f69  mov     edx, edi; i
0x180019f6b  call    DSA_GetItem
0x180019f70  lea     rcx, [rsp+0A8h+var_48]
0x180019f75  jmp     short loc_180019F1B
0x180019f77  mov     eax, edx
0x180019f79  mov     rcx, [rsp+0A8h+var_28]
0x180019f81  xor     rcx, rsp; StackCookie
0x180019f84  call    __security_check_cookie
0x180019f89  mov     rbx, [rsp+0A8h+arg_18]
0x180019f91  add     rsp, 90h
0x180019f98  pop     rdi
0x180019f99  pop     rsi
0x180019f9a  pop     rbp
0x180019f9b  retn
```
