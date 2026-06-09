# CSlowLinkConfigInfo::_LoadInfoIntoPathMap(CPathMap &,ushort const *,void *)

- ea: `0x180011298`
- end: `0x180011434`
- name: `?_LoadInfoIntoPathMap@CSlowLinkConfigInfo@@AEAAJAEAVCPathMap@@PEBGPEAX@Z`
- size: `412`
- prototype: `__int64 __fastcall(CSlowLinkConfigInfo *this, struct CPathMap *, const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180011070`

## callees

- `0x180011298`
- `0x180039610`
- `0x180039650`
- `0x180039fb4`
- `0x180060a3c`
- `0x180060bb4`
- `0x180080788`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011400`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800112ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800112ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800113ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800113ef`

## pseudocode

```c
__int64 __fastcall CSlowLinkConfigInfo::_LoadInfoIntoPathMap(
        CSlowLinkConfigInfo *this,
        struct CPathMap *a2,
        const unsigned __int16 *a3,
        void *a4)
{
  LSTATUS v6; // eax
  DWORD i; // edi
  int v8; // ebx
  unsigned __int64 v9; // rcx
  CSlowLinkConfigInfo *v10; // rcx
  signed int LastError; // eax
  unsigned int *v13; // [rsp+28h] [rbp-D8h]
  DWORD v14; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v15; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cchValueName; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v18; // [rsp+68h] [rbp-98h] BYREF
  __int64 v19; // [rsp+78h] [rbp-88h]
  BYTE v20[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v21[1024]; // [rsp+120h] [rbp+20h] BYREF

  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 1u, &hKey);
  if ( v6 )
  {
    if ( v6 == 2 )
    {
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    for ( i = 0; ; ++i )
    {
      v14 = 0;
      cchValueName = 1024;
      v15 = 160;
      memset_0(v20, 0, 0xA0u);
      v8 = CscReg_EnumValueExpEx(a4, hKey, i, v21, &cchValueName, v13, &v14, v20, &v15);
      if ( v8 >= 0 && v14 == 1 )
      {
        if ( v15 >> 1 >= 0x4F )
        {
          v9 = 158;
        }
        else
        {
          v9 = 2LL * (v15 >> 1);
          if ( v9 >= 0xA0 )
            _report_rangecheckfailure();
        }
        *(_WORD *)&v20[v9] = 0;
        v19 = 0;
        v18 = 0;
        if ( CSlowLinkConfigInfo::_ParseParameterValueString(
               (CSlowLinkConfigInfo *)v9,
               (const unsigned __int16 *)v20,
               (struct CSlowLinkConfigInfo::INFO *)&v18) )
        {
          v8 = CSlowLinkConfigInfo::_AddInfoToPathMap(v10, a2, v21, (const struct CSlowLinkConfigInfo::INFO *)&v18);
        }
      }
      if ( v8 < 0 )
        break;
      if ( (unsigned __int16)v8 == 259 )
        goto LABEL_15;
    }
    if ( (unsigned __int16)v8 != 259 )
      goto LABEL_16;
LABEL_15:
    v8 = 0;
LABEL_16:
    RegCloseKey(hKey);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180011298  push    rbp
0x18001129a  push    rbx
0x18001129b  push    rsi
0x18001129c  push    rdi
0x18001129d  push    r14
0x18001129f  lea     rbp, [rsp-830h]
0x1800112a7  sub     rsp, 930h
0x1800112ae  mov     rax, cs:__security_cookie
0x1800112b5  xor     rax, rsp
0x1800112b8  mov     [rbp+850h+var_30], rax
0x1800112bf  mov     rax, r8
0x1800112c2  mov     [rsp+950h+hKey], 0
0x1800112cb  lea     rcx, [rsp+950h+hKey]
0x1800112d0  mov     r14, r9
0x1800112d3  mov     [rsp+950h+phkResult], rcx; phkResult
0x1800112d8  mov     rsi, rdx
0x1800112db  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800112e2  mov     r9d, 1; samDesired
0x1800112e8  xor     r8d, r8d; ulOptions
0x1800112eb  mov     rdx, rax; lpSubKey
0x1800112ee  call    cs:__imp_RegOpenKeyExW
0x1800112f4  test    eax, eax
0x1800112f6  jnz     loc_1800113F7
0x1800112fc  xor     edi, edi
0x1800112fe  xor     edx, edx; Val
0x180011300  mov     [rsp+950h+var_900], 0
0x180011308  mov     r8d, 0A0h; Size
0x18001130e  mov     [rsp+950h+cchValueName], 400h
0x180011316  lea     rcx, [rbp+850h+var_8D0]; void *
0x18001131a  mov     [rsp+950h+var_8FC], 0A0h
0x180011322  call    memset_0
0x180011327  mov     rdx, [rsp+950h+hKey]; hKey
0x18001132c  lea     rax, [rsp+950h+var_8FC]
0x180011331  mov     [rsp+950h+var_910], rax; LPDWORD
0x180011336  lea     r9, [rbp+850h+var_830]; unsigned __int16 *
0x18001133a  lea     rax, [rbp+850h+var_8D0]
0x18001133e  mov     r8d, edi; dwIndex
0x180011341  mov     [rsp+950h+var_918], rax; LPBYTE
0x180011346  mov     rcx, r14; hToken
0x180011349  lea     rax, [rsp+950h+var_900]
0x18001134e  mov     [rsp+950h+var_920], rax; LPDWORD
0x180011353  lea     rax, [rsp+950h+cchValueName]
0x180011358  mov     [rsp+950h+phkResult], rax; lpcchValueName
0x18001135d  call    ?CscReg_EnumValueExpEx@@YAJPEAXPEAUHKEY__@@KPEAGPEAK33PEAE3@Z; CscReg_EnumValueExpEx(void *,HKEY__ *,ulong,ushort *,ulong *,ulong *,ulong *,uchar *,ulong *)
0x180011362  mov     ebx, eax
0x180011364  test    eax, eax
0x180011366  js      short loc_1800113CC
0x180011368  cmp     [rsp+950h+var_900], 1
0x18001136d  jnz     short loc_1800113CC
0x18001136f  mov     eax, [rsp+950h+var_8FC]
0x180011373  shr     eax, 1
0x180011375  cmp     eax, 4Fh ; 'O'
0x180011378  jnb     short loc_18001138E
0x18001137a  mov     ecx, eax
0x18001137c  add     rcx, rcx
0x18001137f  cmp     rcx, 0A0h
0x180011386  jb      short loc_180011393
0x180011388  call    __report_rangecheckfailure
0x18001138e  mov     ecx, 9Eh; this
0x180011393  xor     eax, eax
0x180011395  lea     r8, [rsp+950h+var_8E8]; struct CSlowLinkConfigInfo::INFO *
0x18001139a  xorps   xmm0, xmm0
0x18001139d  mov     word ptr [rbp+rcx+850h+var_8D0], ax
0x1800113a2  lea     rdx, [rbp+850h+var_8D0]; unsigned __int16 *
0x1800113a6  mov     [rsp+950h+var_8D8], rax
0x1800113ab  movups  [rsp+950h+var_8E8], xmm0
0x1800113b0  call    ?_ParseParameterValueString@CSlowLinkConfigInfo@@AEAAHPEBGPEAUINFO@1@@Z; CSlowLinkConfigInfo::_ParseParameterValueString(ushort const *,CSlowLinkConfigInfo::INFO *)
0x1800113b5  test    eax, eax
0x1800113b7  jz      short loc_1800113CC
0x1800113b9  lea     r9, [rsp+950h+var_8E8]; struct CSlowLinkConfigInfo::INFO *
0x1800113be  mov     rdx, rsi; struct CPathMap *
0x1800113c1  lea     r8, [rbp+850h+var_830]; unsigned __int16 *
0x1800113c5  call    ?_AddInfoToPathMap@CSlowLinkConfigInfo@@AEAAJAEAVCPathMap@@PEBGAEBUINFO@1@@Z; CSlowLinkConfigInfo::_AddInfoToPathMap(CPathMap &,ushort const *,CSlowLinkConfigInfo::INFO const &)
0x1800113ca  mov     ebx, eax
0x1800113cc  movzx   eax, bx
0x1800113cf  test    ebx, ebx
0x1800113d1  js      short loc_1800113E1
0x1800113d3  cmp     eax, 103h
0x1800113d8  jz      short loc_1800113E8
0x1800113da  inc     edi
0x1800113dc  jmp     loc_1800112FE
0x1800113e1  cmp     eax, 103h
0x1800113e6  jnz     short loc_1800113EA
0x1800113e8  xor     ebx, ebx
0x1800113ea  mov     rcx, [rsp+950h+hKey]; hKey
0x1800113ef  call    cs:__imp_RegCloseKey
0x1800113f5  jmp     short loc_180011415
0x1800113f7  cmp     eax, 2
0x1800113fa  jnz     short loc_180011400
0x1800113fc  xor     ebx, ebx
0x1800113fe  jmp     short loc_180011415
0x180011400  call    cs:__imp_GetLastError
0x180011406  mov     ebx, eax
0x180011408  test    eax, eax
0x18001140a  jle     short loc_180011415
0x18001140c  movzx   ebx, ax
0x18001140f  or      ebx, 80070000h
0x180011415  mov     eax, ebx
0x180011417  mov     rcx, [rbp+850h+var_30]
0x18001141e  xor     rcx, rsp; StackCookie
0x180011421  call    __security_check_cookie
0x180011426  add     rsp, 930h
0x18001142d  pop     r14
0x18001142f  pop     rdi
0x180011430  pop     rsi
0x180011431  pop     rbx
0x180011432  pop     rbp
0x180011433  retn
```
