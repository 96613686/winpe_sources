# CreateOutputPin(ushort *,int,_GUID,CKsProxy *,long *,ushort *,int)

- ea: `0x1001a323`
- end: `0x1001a40e`
- name: `?CreateOutputPin@@YGPAVCBasePin@@PAGHU_GUID@@PAVCKsProxy@@PAJ0H@Z`
- size: `235`
- prototype: `struct CBasePin *__stdcall(unsigned __int16 *, int, struct _GUID, struct CKsProxy *, int *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x10009f60`

## callees

- `0x10014357`
- `0x1001a2cc`
- `0x1001a323`
- `0x1001a516`
- `0x1003a6fd`
- `0x1003aba0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1001a387`
- `ADVAPI32!RegQueryValueExW` at `0x1001a387`

## pseudocode

```c
CKsOutputPin *__userpurge CreateOutputPin@<eax>(
        int a1@<edx>,
        HKEY *a2,
        int a3,
        struct _GUID a4,
        struct CKsProxy *a5,
        int *a6,
        unsigned __int16 *a7,
        int a8)
{
  CKsOutputPin2 *v8; // eax
  CKsOutputPin *v10; // eax
  struct _GUID v11; // [esp-20h] [ebp-68h]
  struct _GUID v12; // [esp-20h] [ebp-68h]
  unsigned __int16 *v13; // [esp-4h] [ebp-4Ch]
  unsigned __int16 *v14; // [esp-4h] [ebp-4Ch]
  HKEY v15; // [esp+0h] [ebp-48h]
  struct _GUID *v16; // [esp+4h] [ebp-44h]
  DWORD cbData; // [esp+20h] [ebp-28h] BYREF
  int v18; // [esp+24h] [ebp-24h]
  int v19; // [esp+28h] [ebp-20h]
  unsigned int Data1; // [esp+2Ch] [ebp-1Ch]
  BYTE Data[4]; // [esp+30h] [ebp-18h] BYREF

  v18 = a1;
  v19 = a3;
  Data1 = a4.Data1;
  if ( GetPlginCLSID(v15, v16) < 0
    || (*(_DWORD *)Data = 0, cbData = 4, !RegQueryValueExW(a2[74], L"DisableCustomVidProcHandler", 0, 0, Data, &cbData))
    && *(_DWORD *)Data == 1 )
  {
    v10 = (CKsOutputPin *)operator new(0x2C8u);
    if ( v10 )
    {
      *(_QWORD *)v12.Data4 = __PAIR64__(*(unsigned int *)&a4.Data2, Data1);
      *(_QWORD *)&v12.Data1 = __PAIR64__(v19, (unsigned int)a2);
      return CKsOutputPin::CKsOutputPin(
               v10,
               v14,
               v18,
               v12,
               *(struct CKsProxy **)a4.Data4,
               *(int **)&a4.Data4[4],
               (unsigned __int16 *)a5,
               (int)a6);
    }
  }
  else
  {
    v8 = (CKsOutputPin2 *)operator new(0x338u);
    if ( v8 )
    {
      *(_QWORD *)v11.Data4 = __PAIR64__(*(unsigned int *)&a4.Data2, Data1);
      *(_QWORD *)&v11.Data1 = __PAIR64__(v19, (unsigned int)a2);
      return (CKsOutputPin *)CKsOutputPin2::CKsOutputPin2(
                               v8,
                               v13,
                               v18,
                               v11,
                               *(struct CKsProxy **)a4.Data4,
                               *(int **)&a4.Data4[4],
                               (unsigned __int16 *)a5,
                               (int)a6);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1001a323  mov     edi, edi
0x1001a325  push    ebp
0x1001a326  mov     ebp, esp
0x1001a328  sub     esp, 3Ch
0x1001a32b  mov     eax, ___security_cookie
0x1001a330  xor     eax, ebp
0x1001a332  mov     [ebp+var_4], eax
0x1001a335  mov     eax, dword ptr [ebp+arg_0.Data2]
0x1001a338  push    ebx
0x1001a339  mov     ebx, [ebp+arg_0.Data1]
0x1001a33c  push    esi; struct _GUID *
0x1001a33d  push    edi; HKEY
0x1001a33e  lea     esi, [ebp+arg_10]
0x1001a341  mov     [ebp+var_24], edx
0x1001a344  mov     ecx, [ebx+128h]
0x1001a34a  lea     edi, [ebp+var_38]
0x1001a34d  movsd
0x1001a34e  lea     edx, [ebp+var_14]
0x1001a351  mov     [ebp+var_20], eax
0x1001a354  mov     eax, dword ptr [ebp+arg_0.Data4]
0x1001a357  mov     [ebp+var_1C], eax
0x1001a35a  movsd
0x1001a35b  movsd
0x1001a35c  movsd
0x1001a35d  call    ?GetPlginCLSID@@YGJPAUHKEY__@@PAU_GUID@@@Z; GetPlginCLSID(HKEY__ *,_GUID *)
0x1001a362  xor     esi, esi
0x1001a364  test    eax, eax
0x1001a366  js      short loc_1001A3C9
0x1001a368  lea     eax, [ebp+cbData]
0x1001a36b  mov     dword ptr [ebp+Data], esi
0x1001a36e  push    eax; lpcbData
0x1001a36f  lea     eax, [ebp+Data]
0x1001a372  mov     [ebp+cbData], 4
0x1001a379  push    eax; unsigned __int16 *
0x1001a37a  push    esi; int *
0x1001a37b  push    esi; struct CKsProxy *
0x1001a37c  push    offset aDisablecustomv; "DisableCustomVidProcHandler"
0x1001a381  push    dword ptr [ebx+128h]; hKey
0x1001a387  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x1001a38d  test    eax, eax
0x1001a38f  jnz     short loc_1001A397
0x1001a391  cmp     dword ptr [ebp+Data], 1
0x1001a395  jz      short loc_1001A3C9
0x1001a397  push    338h; int
0x1001a39c  call    ??2@YAPAXI@Z; operator new(uint)
0x1001a3a1  pop     ecx
0x1001a3a2  test    eax, eax
0x1001a3a4  jz      short loc_1001A3FB
0x1001a3a6  sub     esp, 10h
0x1001a3a9  lea     esi, [ebp+var_38]
0x1001a3ac  mov     edi, esp
0x1001a3ae  push    dword ptr [ebp+arg_0.Data4+4]
0x1001a3b1  movsd
0x1001a3b2  push    [ebp+var_1C]
0x1001a3b5  push    [ebp+var_20]
0x1001a3b8  movsd
0x1001a3b9  push    ebx; struct _GUID
0x1001a3ba  push    [ebp+var_24]; int
0x1001a3bd  movsd
0x1001a3be  push    ecx; unsigned __int16 *
0x1001a3bf  mov     ecx, eax; this
0x1001a3c1  movsd
0x1001a3c2  call    ??0CKsOutputPin2@@QAE@PAGHU_GUID@@PAVCKsProxy@@PAJ0H@Z; CKsOutputPin2::CKsOutputPin2(ushort *,int,_GUID,CKsProxy *,long *,ushort *,int)
0x1001a3c7  jmp     short loc_1001A3FD
0x1001a3c9  push    2C8h; int
0x1001a3ce  call    ??2@YAPAXI@Z; operator new(uint)
0x1001a3d3  pop     ecx
0x1001a3d4  test    eax, eax
0x1001a3d6  jz      short loc_1001A3FB
0x1001a3d8  sub     esp, 10h
0x1001a3db  lea     esi, [ebp+var_38]
0x1001a3de  mov     edi, esp
0x1001a3e0  push    dword ptr [ebp+arg_0.Data4+4]
0x1001a3e3  movsd
0x1001a3e4  push    [ebp+var_1C]
0x1001a3e7  push    [ebp+var_20]
0x1001a3ea  movsd
0x1001a3eb  push    ebx; struct _GUID
0x1001a3ec  push    [ebp+var_24]; int
0x1001a3ef  movsd
0x1001a3f0  push    ecx; unsigned __int16 *
0x1001a3f1  mov     ecx, eax; this
0x1001a3f3  movsd
0x1001a3f4  call    ??0CKsOutputPin@@QAE@PAGHU_GUID@@PAVCKsProxy@@PAJ0H@Z; CKsOutputPin::CKsOutputPin(ushort *,int,_GUID,CKsProxy *,long *,ushort *,int)
0x1001a3f9  jmp     short loc_1001A3FD
0x1001a3fb  mov     eax, esi
0x1001a3fd  mov     ecx, [ebp+var_4]
0x1001a400  pop     edi
0x1001a401  pop     esi
0x1001a402  xor     ecx, ebp; StackCookie
0x1001a404  pop     ebx
0x1001a405  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001a40a  leave
0x1001a40b  retn    20h ; ' '
```
