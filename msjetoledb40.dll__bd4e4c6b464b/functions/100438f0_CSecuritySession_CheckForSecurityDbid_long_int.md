# CSecuritySession::CheckForSecurityDbid(long &,int &)

- ea: `0x100438f0`
- end: `0x10043a5b`
- name: `?CheckForSecurityDbid@CSecuritySession@@QAEJAAJAAH@Z`
- size: `363`
- prototype: `int __thiscall(CSecuritySession *__hidden this, int *, int *)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1003fea0`
- `0x10040610`
- `0x100413c0`
- `0x10041890`
- `0x10041f50`
- `0x100429a0`

## callees

- `0x100198d0`
- `0x100438f0`
- `0x1004d420`

## import_xrefs

- `msjet40!__imp__JetCloseDatabase@12` at `0x10043a25`
- `msjet40!__imp__JetCloseDatabase@12` at `0x10043a25`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100439b7`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100439d9`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100439b7`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100439d9`
- `msjet40!__imp__JetGetSystemParameter@24` at `0x10043958`
- `msjet40!__imp__JetGetSystemParameter@24` at `0x10043958`

## pseudocode

```c
int __thiscall CSecuritySession::CheckForSecurityDbid(CSecuritySession *this, int *a2, int *a3)
{
  unsigned int *v3; // edi
  bool v4; // zf
  unsigned int *v5; // esi
  int SystemParameter; // eax
  int v7; // esi
  int DatabaseInfo; // eax
  int v9; // eax
  int v11; // [esp+10h] [ebp-230h] BYREF
  _BYTE v12[4]; // [esp+18h] [ebp-228h] BYREF
  int *v13; // [esp+1Ch] [ebp-224h]
  int v14; // [esp+20h] [ebp-220h] BYREF
  CSecuritySession *v15; // [esp+24h] [ebp-21Ch]
  unsigned __int16 v16[266]; // [esp+28h] [ebp-218h] BYREF

  v3 = (unsigned int *)((char *)this + 8);
  v15 = this;
  *a3 = 0;
  v4 = *((_DWORD *)this + 2) == -1;
  v13 = a3;
  v14 = 0;
  if ( v4 )
  {
    v5 = (unsigned int *)((char *)this + 4);
    SystemParameter = JetGetSystemParameter(
                        *(_DWORD *)(*((_DWORD *)this + 4) + 96),
                        *((_DWORD *)this + 1),
                        0,
                        v12,
                        v16,
                        260);
    *a2 = SystemParameter;
    if ( SystemParameter >= 0 )
    {
      v7 = CDataSource::JETOpenDatabase(*((CDataSource **)v15 + 4), v5, v3, (unsigned int *)a2, v16, 0);
      if ( v7 < 0 )
      {
        if ( *a2 < 0 )
          *v13 = 1;
        *v3 = -1;
        goto LABEL_14;
      }
      DatabaseInfo = JetGetDatabaseInfo(*((_DWORD *)v15 + 1), *v3, &v11, 8, 9);
      *a2 = DatabaseInfo;
      if ( DatabaseInfo >= 0 )
      {
        v9 = JetGetDatabaseInfo(*((_DWORD *)v15 + 1), *v3, &v14, 4, 8);
        *a2 = v9;
        if ( v9 >= 0 )
        {
          if ( (v11 == 21 || v11 == 1) && (v14 & 0xFFFF0000) >= 0x40000 )
            return v7;
          *a2 = -1815;
        }
      }
    }
    v7 = -2147467259;
LABEL_14:
    if ( *v3 != -1 )
    {
      JetCloseDatabase(*((_DWORD *)v15 + 1), *v3, 0);
      *v3 = -1;
    }
    return v7;
  }
  return 0;
}

```

## disassembly

```asm
0x100438f0  mov     edi, edi
0x100438f2  push    ebp
0x100438f3  mov     ebp, esp
0x100438f5  sub     esp, 234h
0x100438fb  mov     eax, ___security_cookie
0x10043900  xor     eax, ebp
0x10043902  mov     [ebp+var_4], eax
0x10043905  push    ebx
0x10043906  mov     ebx, [ebp+arg_0]
0x10043909  mov     eax, ecx
0x1004390b  mov     ecx, [ebp+arg_4]
0x1004390e  push    esi
0x1004390f  push    edi
0x10043910  lea     edi, [eax+8]
0x10043913  mov     [ebp+var_21C], eax
0x10043919  mov     dword ptr [ecx], 0
0x1004391f  cmp     dword ptr [edi], 0FFFFFFFFh
0x10043922  mov     [ebp+var_224], ecx
0x10043928  mov     [ebp+var_220], 0
0x10043932  jnz     loc_10043A46
0x10043938  push    104h
0x1004393d  lea     ecx, [ebp+var_218]
0x10043943  push    ecx
0x10043944  lea     ecx, [ebp+var_228]
0x1004394a  push    ecx
0x1004394b  lea     esi, [eax+4]
0x1004394e  mov     eax, [eax+10h]
0x10043951  push    0
0x10043953  push    dword ptr [esi]
0x10043955  push    dword ptr [eax+60h]
0x10043958  call    ds:__imp__JetGetSystemParameter@24; JetGetSystemParameter(x,x,x,x,x,x)
0x1004395e  mov     [ebx], eax
0x10043960  test    eax, eax
0x10043962  js      loc_10043A0D
0x10043968  mov     ecx, [ebp+var_21C]
0x1004396e  lea     eax, [ebp+var_218]
0x10043974  push    0; unsigned int *
0x10043976  push    eax; unsigned __int16 *
0x10043977  push    ebx; int *
0x10043978  mov     ecx, [ecx+10h]; this
0x1004397b  push    edi; unsigned int *
0x1004397c  push    esi; unsigned int *
0x1004397d  call    ?JETOpenDatabase@CDataSource@@QAEJAAK0AAJPAGPAK@Z; CDataSource::JETOpenDatabase(ulong &,ulong &,long &,ushort *,ulong *)
0x10043982  mov     esi, eax
0x10043984  test    esi, esi
0x10043986  jns     short loc_100439A1
0x10043988  cmp     dword ptr [ebx], 0
0x1004398b  jge     short loc_10043999
0x1004398d  mov     eax, [ebp+var_224]
0x10043993  mov     dword ptr [eax], 1
0x10043999  mov     dword ptr [edi], 0FFFFFFFFh
0x1004399f  jmp     short loc_10043A12
0x100439a1  push    9
0x100439a3  push    8
0x100439a5  lea     eax, [ebp+var_230]
0x100439ab  push    eax
0x100439ac  mov     eax, [ebp+var_21C]
0x100439b2  push    dword ptr [edi]
0x100439b4  push    dword ptr [eax+4]
0x100439b7  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x100439bd  mov     [ebx], eax
0x100439bf  test    eax, eax
0x100439c1  js      short loc_10043A0D
0x100439c3  push    8
0x100439c5  push    4
0x100439c7  lea     eax, [ebp+var_220]
0x100439cd  push    eax
0x100439ce  mov     eax, [ebp+var_21C]
0x100439d4  push    dword ptr [edi]
0x100439d6  push    dword ptr [eax+4]
0x100439d9  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x100439df  mov     [ebx], eax
0x100439e1  test    eax, eax
0x100439e3  js      short loc_10043A0D
0x100439e5  mov     eax, [ebp+var_230]
0x100439eb  cmp     eax, 15h
0x100439ee  jz      short loc_100439F5
0x100439f0  cmp     eax, 1
0x100439f3  jnz     short loc_10043A07
0x100439f5  mov     eax, [ebp+var_220]
0x100439fb  and     eax, 0FFFF0000h
0x10043a00  cmp     eax, 40000h
0x10043a05  jnb     short loc_10043A31
0x10043a07  mov     dword ptr [ebx], 0FFFFF8E9h
0x10043a0d  mov     esi, 80004005h
0x10043a12  mov     eax, [edi]
0x10043a14  cmp     eax, 0FFFFFFFFh
0x10043a17  jz      short loc_10043A31
0x10043a19  push    0; grbit
0x10043a1b  push    eax; dbid
0x10043a1c  mov     eax, [ebp+var_21C]
0x10043a22  push    dword ptr [eax+4]; sesid
0x10043a25  call    ds:__imp__JetCloseDatabase@12; JetCloseDatabase(x,x,x)
0x10043a2b  mov     dword ptr [edi], 0FFFFFFFFh
0x10043a31  mov     eax, esi
0x10043a33  pop     edi
0x10043a34  pop     esi
0x10043a35  pop     ebx
0x10043a36  mov     ecx, [ebp+var_4]
0x10043a39  xor     ecx, ebp; StackCookie
0x10043a3b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10043a40  mov     esp, ebp
0x10043a42  pop     ebp
0x10043a43  retn    8
0x10043a46  mov     ecx, [ebp+var_4]
0x10043a49  xor     eax, eax
0x10043a4b  pop     edi
0x10043a4c  pop     esi
0x10043a4d  xor     ecx, ebp; StackCookie
0x10043a4f  pop     ebx
0x10043a50  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10043a55  mov     esp, ebp
0x10043a57  pop     ebp
0x10043a58  retn    8
```
