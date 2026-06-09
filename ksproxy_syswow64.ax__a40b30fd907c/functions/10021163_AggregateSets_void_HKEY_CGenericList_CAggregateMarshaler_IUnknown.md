# AggregateSets(void *,HKEY__ *,CGenericList<CAggregateMarshaler> *,IUnknown *)

- ea: `0x10021163`
- end: `0x1002138b`
- name: `?AggregateSets@@YGJPAXPAUHKEY__@@PAV?$CGenericList@VCAggregateMarshaler@@@@PAUIUnknown@@@Z`
- size: `552`
- prototype: `int __fastcall(DWORD, HKEY, CBaseList *, IUnknown *)`
- caller_count: `8`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x1000cf60`
- `0x100113e0`
- `0x100115a5`
- `0x10011c70`
- `0x10014ed0`
- `0x100150a0`
- `0x10015b70`
- `0x1001a8f0`

## callees

- `0x10020bea`
- `0x10020f9f`
- `0x10021163`
- `0x100213de`
- `0x1002d510`
- `0x1003a6f2`
- `0x1003a6fd`
- `0x1003aba0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1002126e`
- `ADVAPI32!RegQueryValueExW` at `0x100212cf`
- `ADVAPI32!RegQueryValueExW` at `0x1002126e`
- `ADVAPI32!RegQueryValueExW` at `0x100212cf`
- `ADVAPI32!RegCloseKey` at `0x100212da`
- `ADVAPI32!RegCloseKey` at `0x10021333`
- `ADVAPI32!RegCloseKey` at `0x10021342`
- `ADVAPI32!RegCloseKey` at `0x10021359`
- `ADVAPI32!RegCloseKey` at `0x100212da`
- `ADVAPI32!RegCloseKey` at `0x10021333`
- `ADVAPI32!RegCloseKey` at `0x10021342`
- `ADVAPI32!RegCloseKey` at `0x10021359`
- `ADVAPI32!RegOpenKeyExW` at `0x100211f8`
- `ADVAPI32!RegOpenKeyExW` at `0x1002121f`
- `ADVAPI32!RegOpenKeyExW` at `0x100212ac`
- `ADVAPI32!RegOpenKeyExW` at `0x100211f8`
- `ADVAPI32!RegOpenKeyExW` at `0x1002121f`
- `ADVAPI32!RegOpenKeyExW` at `0x100212ac`
- `ole32!StringFromGUID2` at `0x1002124a`
- `ole32!StringFromGUID2` at `0x10021293`
- `ole32!StringFromGUID2` at `0x1002124a`
- `ole32!StringFromGUID2` at `0x10021293`

## pseudocode

```c
int __fastcall AggregateSets(DWORD a1, HKEY a2, CBaseList *a3, IUnknown *a4)
{
  void *v4; // eax
  CBaseList::CNode *m_pFirst; // edi
  HKEY v6; // esi
  _DWORD *m_pObject; // eax
  int v8; // ecx
  HKEY v9; // ebx
  unsigned int *v10; // edi
  LSTATUS v11; // esi
  GUID *v12; // eax
  unsigned int *v13; // esi
  CBaseList *v14; // ecx
  struct _GUID **v16; // [esp+0h] [ebp-98h]
  unsigned int *v17; // [esp+4h] [ebp-94h]
  GUID *rguid; // [esp+14h] [ebp-84h]
  HKEY phkResult; // [esp+1Ch] [ebp-7Ch] BYREF
  DWORD cbData; // [esp+20h] [ebp-78h] BYREF
  HKEY hKey; // [esp+24h] [ebp-74h] BYREF
  HKEY v22; // [esp+28h] [ebp-70h] BYREF
  void *Block; // [esp+2Ch] [ebp-6Ch] BYREF
  GUID Data; // [esp+30h] [ebp-68h] BYREF
  OLECHAR sz[42]; // [esp+40h] [ebp-58h] BYREF

  v4 = (void *)a1;
  m_pFirst = a3->m_pFirst;
  v6 = a2;
  v22 = a2;
  cbData = a1;
  if ( m_pFirst )
  {
    do
    {
      m_pObject = m_pFirst->m_pObject;
      m_pFirst = m_pFirst->m_pNext;
      if ( !m_pObject[10] && !m_pObject[11] )
      {
        v8 = m_pObject[9];
        if ( v8 )
        {
          m_pObject[11] = 1;
          (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v8 + 28))(*(_DWORD *)(*(_DWORD *)v8 + 28), v8);
        }
      }
    }
    while ( m_pFirst );
    v6 = v22;
    v4 = (void *)cbData;
  }
  CollectAllSets(&Block, v4, (DWORD *)&v22, v16, v17);
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\MediaInterfaces",
         0,
         0x20019u,
         &phkResult) )
  {
    if ( Block )
      operator delete[](Block);
    goto LABEL_28;
  }
  if ( !Block )
  {
    RegCloseKey(phkResult);
LABEL_28:
    v14 = a3;
    goto LABEL_29;
  }
  if ( RegOpenKeyExW(v6, L"SetAliases", 0, 0x20019u, &hKey) )
    hKey = 0;
  v9 = v22;
  while ( v9 )
  {
    v9 = (HKEY)((char *)v9 - 1);
    rguid = (GUID *)((char *)Block + 16 * (_DWORD)v9);
    StringFromGUID2(rguid, sz, 39);
    if ( hKey )
    {
      cbData = 16;
      if ( !RegQueryValueExW(hKey, sz, 0, 0, (LPBYTE)&Data, &cbData) )
      {
        v10 = (unsigned int *)((char *)Block + 16 * (_DWORD)v9);
        *v10++ = Data.Data1;
        *v10++ = *(_DWORD *)&Data.Data2;
        *v10 = *(_DWORD *)Data.Data4;
        v10[1] = *(_DWORD *)&Data.Data4[4];
        StringFromGUID2(rguid, sz, 39);
      }
    }
    if ( !RegOpenKeyExW(phkResult, sz, 0, 0x20019u, &v22) )
    {
      cbData = 16;
      v11 = RegQueryValueExW(v22, L"iid", 0, 0, (LPBYTE)&Data, &cbData);
      RegCloseKey(v22);
      if ( v11 )
        Data = _GUID_00000000_0000_0000_0000_000000000000;
      v12 = (GUID *)operator new(0x30u);
      if ( !v12 )
        break;
      *v12 = Data;
      v13 = (unsigned int *)((char *)Block + 16 * (_DWORD)v9);
      v12[1].Data1 = *v13++;
      *(_DWORD *)&v12[1].Data2 = *v13++;
      *(_DWORD *)v12[1].Data4 = *v13;
      *(_DWORD *)&v12[1].Data4[4] = v13[1];
      AddAggregateObject(a3, (int)v12, a4, 1);
    }
  }
  RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  operator delete[](Block);
  v14 = a3;
LABEL_29:
  UnloadVolatileInterfaces(v14, 0);
  return 0;
}

```

## disassembly

```asm
0x10021163  mov     edi, edi
0x10021165  push    ebp
0x10021166  mov     ebp, esp
0x10021168  sub     esp, 8Ch
0x1002116e  mov     eax, ___security_cookie
0x10021173  xor     eax, ebp
0x10021175  mov     [ebp+var_4], eax
0x10021178  push    ebx
0x10021179  mov     ebx, [ebp+arg_0]
0x1002117c  mov     eax, ecx
0x1002117e  mov     ecx, [ebp+arg_4]
0x10021181  push    esi; unsigned int *
0x10021182  push    edi; struct _GUID **
0x10021183  mov     edi, [ebx]
0x10021185  mov     esi, edx
0x10021187  mov     [ebp+var_70], esi
0x1002118a  mov     [ebp+cbData], eax
0x1002118d  mov     [ebp+var_80], ebx
0x10021190  mov     [ebp+var_88], ecx
0x10021196  test    edi, edi
0x10021198  jz      short loc_100211D4
0x1002119a  mov     eax, [edi+8]
0x1002119d  mov     edi, [edi+4]
0x100211a0  cmp     dword ptr [eax+28h], 0
0x100211a4  jnz     short loc_100211CA
0x100211a6  cmp     dword ptr [eax+2Ch], 0
0x100211aa  jnz     short loc_100211CA
0x100211ac  mov     ecx, [eax+24h]
0x100211af  test    ecx, ecx
0x100211b1  jz      short loc_100211CA
0x100211b3  mov     dword ptr [eax+2Ch], 1
0x100211ba  mov     eax, [ecx]
0x100211bc  push    ecx
0x100211bd  mov     esi, [eax+1Ch]
0x100211c0  mov     ecx, esi; this
0x100211c2  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100211c8  call    esi
0x100211ca  test    edi, edi
0x100211cc  jnz     short loc_1002119A
0x100211ce  mov     esi, [ebp+var_70]
0x100211d1  mov     eax, [ebp+cbData]
0x100211d4  lea     ecx, [ebp+var_70]
0x100211d7  push    ecx; void *
0x100211d8  lea     edx, [ebp+Block]
0x100211db  mov     ecx, eax
0x100211dd  call    ?CollectAllSets@@YGJPAXPAPAU_GUID@@PAK@Z; CollectAllSets(void *,_GUID * *,ulong *)
0x100211e2  lea     eax, [ebp+phkResult]
0x100211e5  xor     edi, edi
0x100211e7  push    eax; phkResult
0x100211e8  push    20019h; samDesired
0x100211ed  push    edi; ulOptions
0x100211ee  push    offset aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Med"...
0x100211f3  push    80000002h; hKey
0x100211f8  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x100211fe  test    eax, eax
0x10021200  jnz     loc_10021361
0x10021206  cmp     [ebp+Block], edi
0x10021209  jz      loc_10021356
0x1002120f  lea     eax, [ebp+hKey]
0x10021212  push    eax; phkResult
0x10021213  push    20019h; samDesired
0x10021218  push    edi; ulOptions
0x10021219  push    offset aSetaliases; "SetAliases"
0x1002121e  push    esi; hKey
0x1002121f  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x10021225  test    eax, eax
0x10021227  jz      short loc_1002122C
0x10021229  mov     [ebp+hKey], edi
0x1002122c  mov     ebx, [ebp+var_70]
0x1002122f  jmp     loc_10021328
0x10021234  dec     ebx
0x10021235  lea     ecx, [ebp+sz]
0x10021238  mov     eax, ebx
0x1002123a  push    27h ; '''; cchMax
0x1002123c  shl     eax, 4
0x1002123f  add     eax, [ebp+Block]
0x10021242  push    ecx; lpsz
0x10021243  push    eax; rguid
0x10021244  mov     [ebp+rguid], eax
0x1002124a  call    ds:__imp__StringFromGUID2@12; StringFromGUID2(x,x,x)
0x10021250  cmp     [ebp+hKey], 0
0x10021254  jz      short loc_1002129B
0x10021256  lea     eax, [ebp+cbData]
0x10021259  mov     [ebp+cbData], 10h
0x10021260  push    eax; lpcbData
0x10021261  lea     eax, [ebp+Data]
0x10021264  push    eax; lpData
0x10021265  push    edi; lpType
0x10021266  push    edi; lpReserved
0x10021267  lea     eax, [ebp+sz]
0x1002126a  push    eax; lpValueName
0x1002126b  push    [ebp+hKey]; hKey
0x1002126e  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x10021274  test    eax, eax
0x10021276  jnz     short loc_1002129B
0x10021278  mov     edi, ebx
0x1002127a  lea     esi, [ebp+Data]
0x1002127d  shl     edi, 4
0x10021280  lea     eax, [ebp+sz]
0x10021283  add     edi, [ebp+Block]
0x10021286  push    27h ; '''; cchMax
0x10021288  push    eax; lpsz
0x10021289  push    [ebp+rguid]; rguid
0x1002128f  movsd
0x10021290  movsd
0x10021291  movsd
0x10021292  movsd
0x10021293  call    ds:__imp__StringFromGUID2@12; StringFromGUID2(x,x,x)
0x10021299  xor     edi, edi
0x1002129b  lea     eax, [ebp+var_70]
0x1002129e  push    eax; phkResult
0x1002129f  push    20019h; samDesired
0x100212a4  push    edi; ulOptions
0x100212a5  lea     eax, [ebp+sz]
0x100212a8  push    eax; lpSubKey
0x100212a9  push    [ebp+phkResult]; hKey
0x100212ac  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x100212b2  test    eax, eax
0x100212b4  jnz     short loc_10021328
0x100212b6  lea     eax, [ebp+cbData]
0x100212b9  mov     [ebp+cbData], 10h
0x100212c0  push    eax; lpcbData
0x100212c1  lea     eax, [ebp+Data]
0x100212c4  push    eax; lpData
0x100212c5  push    edi; lpType
0x100212c6  push    edi; lpReserved
0x100212c7  push    offset aIid; "iid"
0x100212cc  push    [ebp+var_70]; hKey
0x100212cf  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x100212d5  push    [ebp+var_70]; hKey
0x100212d8  mov     esi, eax
0x100212da  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x100212e0  test    esi, esi
0x100212e2  jz      short loc_100212F0
0x100212e4  mov     esi, offset __GUID_00000000_0000_0000_0000_000000000000
0x100212e9  lea     edi, [ebp+Data]
0x100212ec  movsd
0x100212ed  movsd
0x100212ee  movsd
0x100212ef  movsd
0x100212f0  push    30h ; '0'; Size
0x100212f2  call    ??2@YAPAXI@Z; operator new(uint)
0x100212f7  pop     ecx
0x100212f8  test    eax, eax
0x100212fa  jz      short loc_10021330
0x100212fc  mov     edi, eax
0x100212fe  mov     ecx, [ebp+var_80]
0x10021301  lea     esi, [ebp+Data]
0x10021304  mov     edx, eax
0x10021306  push    1
0x10021308  push    [ebp+var_88]
0x1002130e  movsd
0x1002130f  movsd
0x10021310  movsd
0x10021311  movsd
0x10021312  mov     esi, ebx
0x10021314  lea     edi, [eax+10h]
0x10021317  shl     esi, 4
0x1002131a  add     esi, [ebp+Block]
0x1002131d  movsd
0x1002131e  movsd
0x1002131f  movsd
0x10021320  movsd
0x10021321  call    ?AddAggregateObject@@YGJPAV?$CGenericList@VCAggregateMarshaler@@@@PAVCAggregateMarshaler@@PAUIUnknown@@H@Z; AddAggregateObject(CGenericList<CAggregateMarshaler> *,CAggregateMarshaler *,IUnknown *,int)
0x10021326  xor     edi, edi
0x10021328  test    ebx, ebx
0x1002132a  jnz     loc_10021234
0x10021330  push    [ebp+phkResult]; hKey
0x10021333  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10021339  cmp     [ebp+hKey], 0
0x1002133d  jz      short loc_10021348
0x1002133f  push    [ebp+hKey]; hKey
0x10021342  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10021348  push    [ebp+Block]; Block
0x1002134b  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10021350  pop     ecx
0x10021351  mov     ecx, [ebp+var_80]
0x10021354  jmp     short loc_10021371
0x10021356  push    [ebp+phkResult]; hKey
0x10021359  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x1002135f  jmp     short loc_1002136F
0x10021361  cmp     [ebp+Block], edi
0x10021364  jz      short loc_1002136F
0x10021366  push    [ebp+Block]; Block
0x10021369  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002136e  pop     ecx
0x1002136f  mov     ecx, ebx
0x10021371  xor     edx, edx
0x10021373  call    ?UnloadVolatileInterfaces@@YGXPAV?$CGenericList@VCAggregateMarshaler@@@@H@Z; UnloadVolatileInterfaces(CGenericList<CAggregateMarshaler> *,int)
0x10021378  mov     ecx, [ebp+var_4]
0x1002137b  xor     eax, eax
0x1002137d  pop     edi
0x1002137e  pop     esi
0x1002137f  xor     ecx, ebp; StackCookie
0x10021381  pop     ebx
0x10021382  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10021387  leave
0x10021388  retn    8
```
