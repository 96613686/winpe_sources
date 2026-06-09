# MFCreateRemoteDesktopPlugin

- ea: `0x180044b70`
- end: `0x180044db1`
- name: `MFCreateRemoteDesktopPlugin`
- size: `577`
- prototype: `HRESULT __stdcall(IMFRemoteDesktopPlugin **ppPlugin)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000f370`
- `0x1800104b0`
- `0x180010600`
- `0x180018e70`
- `0x18001c5c0`
- `0x180034b38`
- `0x180036828`
- `0x180044b70`
- `0x180048f0c`
- `0x180065ec0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180044d53`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180044d53`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044bc6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044cb6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044bc6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044cb6`

## string_xrefs

- `0x180044b8f`: `MFCreateRemoteDesktopPlugin`
- `0x180044c24`: `MFCreateRemoteDesktopPlugin`
- `0x180044d14`: `MFCreateRemoteDesktopPlugin`

## pseudocode

```c
HRESULT __stdcall MFCreateRemoteDesktopPlugin(IMFRemoteDesktopPlugin **ppPlugin)
{
  __int64 *v2; // rcx
  int v3; // ebx
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  _BYTE v11[8]; // [rsp+30h] [rbp-28h] BYREF
  IID rclsid; // [rsp+38h] [rbp-20h] BYREF

  rclsid = (IID)xmmword_180072400;
  sub_18000F370(v11, "MFCreateRemoteDesktopPlugin", 27);
  if ( ppPlugin )
  {
    *ppPlugin = 0;
    if ( (unsigned int)sub_180048F0C() )
    {
      v3 = CoCreateInstance(&rclsid, 0, 1u, &stru_18006F438, (LPVOID *)ppPlugin);
      if ( v3 < 0 )
      {
        v3 = -2147467263;
      }
      else if ( byte_180084959 )
      {
        sub_180036828(*((_QWORD *)RequestContext + 7), 14, &unk_1800723F0);
      }
    }
    else
    {
      if ( byte_180084959 )
        sub_180036828(*((_QWORD *)RequestContext + 7), 12, &unk_1800723F0);
      v7 = (__int64 *)qword_180084A30;
      v3 = -2147024891;
      if ( !qword_180084A30 )
      {
        v8 = MFGetCallStackTracingWeakReference(0);
        qword_180084A30 = v8;
        if ( v8 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
        {
          v7 = (__int64 *)qword_180084A30;
        }
        else
        {
          v7 = &qword_180083DB0;
          qword_180084A30 = (__int64)&qword_180083DB0;
        }
      }
      if ( *((_BYTE *)v7 + 8) )
      {
        v9 = sub_180010600();
        if ( *(_DWORD *)(v9 + 1996) != -2147024891 )
          sub_180034B38(v9, "MFCreateRemoteDesktopPlugin", 61, 2147942405LL);
      }
      if ( byte_180084958 )
      {
        v6 = 13;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v2 = (__int64 *)qword_180084A30;
    v3 = -2147467261;
    if ( !qword_180084A30 )
    {
      v4 = MFGetCallStackTracingWeakReference(0);
      qword_180084A30 = v4;
      if ( v4 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 8LL))(v4, 2032) )
      {
        v2 = (__int64 *)qword_180084A30;
      }
      else
      {
        v2 = &qword_180083DB0;
        qword_180084A30 = (__int64)&qword_180083DB0;
      }
    }
    if ( *((_BYTE *)v2 + 8) )
    {
      v5 = sub_180010600();
      if ( *(_DWORD *)(v5 + 1996) != -2147467261 )
        sub_180034B38(v5, "MFCreateRemoteDesktopPlugin", 27, 2147500035LL);
    }
    if ( byte_180084958 )
    {
      v6 = 10;
LABEL_12:
      sub_180018E70(*((_QWORD *)RequestContext + 2), v6, &unk_1800723F0, 0, v3);
    }
  }
  sub_1800104B0(v11);
  return v3;
}

```

## disassembly

```asm
0x180044b70  push    rbx
0x180044b72  sub     rsp, 50h
0x180044b76  mov     rax, cs:__security_cookie
0x180044b7d  xor     rax, rsp
0x180044b80  mov     [rsp+58h+var_10], rax
0x180044b85  movups  xmm0, cs:xmmword_180072400
0x180044b8c  mov     rbx, rcx
0x180044b8f  lea     rdx, aMfcreateremote_0; "MFCreateRemoteDesktopPlugin"
0x180044b96  mov     r8d, 1Bh
0x180044b9c  lea     rcx, [rsp+58h+var_28]
0x180044ba1  movdqu  xmmword ptr [rsp+58h+rclsid.Data1], xmm0
0x180044ba7  call    sub_18000F370
0x180044bac  test    rbx, rbx
0x180044baf  jnz     loc_180044C6E
0x180044bb5  mov     rcx, cs:qword_180084A30
0x180044bbc  mov     ebx, 80004003h
0x180044bc1  test    rcx, rcx
0x180044bc4  jnz     short loc_180044C0E
0x180044bc6  call    cs:MFGetCallStackTracingWeakReference
0x180044bcd  nop     dword ptr [rax+rax+00h]
0x180044bd2  mov     cs:qword_180084A30, rax
0x180044bd9  mov     rcx, rax
0x180044bdc  test    rax, rax
0x180044bdf  jz      short loc_180044C00
0x180044be1  mov     rax, [rax]
0x180044be4  mov     edx, 7F0h
0x180044be9  mov     rax, [rax+8]
0x180044bed  call    cs:__guard_dispatch_icall_fptr
0x180044bf3  test    eax, eax
0x180044bf5  jz      short loc_180044C00
0x180044bf7  mov     rcx, cs:qword_180084A30
0x180044bfe  jmp     short loc_180044C0E
0x180044c00  lea     rcx, qword_180083DB0
0x180044c07  mov     cs:qword_180084A30, rcx
0x180044c0e  cmp     byte ptr [rcx+8], 0
0x180044c12  jz      short loc_180044C39
0x180044c14  call    sub_180010600
0x180044c19  cmp     [rax+7CCh], ebx
0x180044c1f  jz      short loc_180044C39
0x180044c21  mov     r9d, ebx
0x180044c24  lea     rdx, aMfcreateremote_0; "MFCreateRemoteDesktopPlugin"
0x180044c2b  mov     r8d, 1Bh
0x180044c31  mov     rcx, rax
0x180044c34  call    sub_180034B38
0x180044c39  cmp     cs:byte_180084958, 1
0x180044c40  jb      loc_180044D91
0x180044c46  mov     edx, 0Ah
0x180044c4b  mov     rcx, cs:RequestContext
0x180044c52  lea     r8, unk_1800723F0
0x180044c59  xor     r9d, r9d
0x180044c5c  mov     dword ptr [rsp+58h+ppv], ebx
0x180044c60  mov     rcx, [rcx+10h]
0x180044c64  call    sub_180018E70
0x180044c69  jmp     loc_180044D91
0x180044c6e  mov     qword ptr [rbx], 0
0x180044c75  call    sub_180048F0C
0x180044c7a  test    eax, eax
0x180044c7c  jnz     loc_180044D3C
0x180044c82  cmp     cs:byte_180084959, 1
0x180044c89  jb      short loc_180044CA5
0x180044c8b  mov     rcx, cs:RequestContext
0x180044c92  lea     edx, [rax+0Ch]
0x180044c95  lea     r8, unk_1800723F0
0x180044c9c  mov     rcx, [rcx+38h]
0x180044ca0  call    sub_180036828
0x180044ca5  mov     rcx, cs:qword_180084A30
0x180044cac  mov     ebx, 80070005h
0x180044cb1  test    rcx, rcx
0x180044cb4  jnz     short loc_180044CFE
0x180044cb6  call    cs:MFGetCallStackTracingWeakReference
0x180044cbd  nop     dword ptr [rax+rax+00h]
0x180044cc2  mov     cs:qword_180084A30, rax
0x180044cc9  mov     rcx, rax
0x180044ccc  test    rax, rax
0x180044ccf  jz      short loc_180044CF0
0x180044cd1  mov     rax, [rax]
0x180044cd4  mov     edx, 7F0h
0x180044cd9  mov     rax, [rax+8]
0x180044cdd  call    cs:__guard_dispatch_icall_fptr
0x180044ce3  test    eax, eax
0x180044ce5  jz      short loc_180044CF0
0x180044ce7  mov     rcx, cs:qword_180084A30
0x180044cee  jmp     short loc_180044CFE
0x180044cf0  lea     rcx, qword_180083DB0
0x180044cf7  mov     cs:qword_180084A30, rcx
0x180044cfe  cmp     byte ptr [rcx+8], 0
0x180044d02  jz      short loc_180044D29
0x180044d04  call    sub_180010600
0x180044d09  cmp     [rax+7CCh], ebx
0x180044d0f  jz      short loc_180044D29
0x180044d11  mov     r9d, ebx
0x180044d14  lea     rdx, aMfcreateremote_0; "MFCreateRemoteDesktopPlugin"
0x180044d1b  mov     r8d, 3Dh ; '='
0x180044d21  mov     rcx, rax
0x180044d24  call    sub_180034B38
0x180044d29  cmp     cs:byte_180084958, 1
0x180044d30  jb      short loc_180044D91
0x180044d32  mov     edx, 0Dh
0x180044d37  jmp     loc_180044C4B
0x180044d3c  xor     edx, edx; pUnkOuter
0x180044d3e  mov     [rsp+58h+ppv], rbx; ppv
0x180044d43  lea     r9, stru_18006F438; riid
0x180044d4a  lea     rcx, [rsp+58h+rclsid]; rclsid
0x180044d4f  lea     r8d, [rdx+1]; dwClsContext
0x180044d53  call    cs:CoCreateInstance
0x180044d5a  nop     dword ptr [rax+rax+00h]
0x180044d5f  mov     ebx, eax
0x180044d61  test    eax, eax
0x180044d63  js      short loc_180044D8C
0x180044d65  cmp     cs:byte_180084959, 1
0x180044d6c  jb      short loc_180044D91
0x180044d6e  mov     rcx, cs:RequestContext
0x180044d75  lea     r8, unk_1800723F0
0x180044d7c  mov     edx, 0Eh
0x180044d81  mov     rcx, [rcx+38h]
0x180044d85  call    sub_180036828
0x180044d8a  jmp     short loc_180044D91
0x180044d8c  mov     ebx, 80004001h
0x180044d91  lea     rcx, [rsp+58h+var_28]
0x180044d96  call    sub_1800104B0
0x180044d9b  mov     eax, ebx
0x180044d9d  mov     rcx, [rsp+58h+var_10]
0x180044da2  xor     rcx, rsp; StackCookie
0x180044da5  call    __security_check_cookie
0x180044daa  add     rsp, 50h
0x180044dae  pop     rbx
0x180044daf  retn
```
