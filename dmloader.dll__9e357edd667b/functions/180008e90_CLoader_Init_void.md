# CLoader::Init(void)

- ea: `0x180008e90`
- end: `0x1800092ac`
- name: `?Init@CLoader@@QEAAJXZ`
- size: `1052`
- prototype: `__int64 __fastcall(CLoader *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180003bd0`

## callees

- `0x1800015d0`
- `0x1800019a0`
- `0x180001ef0`
- `0x1800089e4`
- `0x180008e90`
- `0x180009fdc`
- `0x18000a10c`
- `0x18000a178`
- `0x18000a908`
- `0x18000abec`
- `0x18000ad04`
- `0x18000b358`
- `0x18000b45c`
- `0x18000b668`
- `0x18000b81c`
- `0x18000c018`
- `0x180010010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800091f2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800091f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800090dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800090dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800091d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800091d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008fd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008fd3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008eff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008eff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008f3f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008f3f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180008f6e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180008f6e`

## string_xrefs

- `0x180008f38`: `GMFilePath`

## pseudocode

```c
__int64 __fastcall CLoader::Init(CLoader *this)
{
  __int64 v2; // rbx
  __int64 v3; // rdi
  LSTATUS v4; // r14d
  __int64 v5; // rcx
  WCHAR *v6; // r8
  __int64 v7; // rdx
  BYTE *v8; // rax
  BYTE *v9; // rcx
  BYTE *v10; // rcx
  char *v11; // rax
  char *v12; // rcx
  int v13; // eax
  struct IStream *v14; // rdi
  struct IStream v15; // rax
  _DWORD *v16; // rbx
  _QWORD *v17; // rax
  _QWORD *v18; // rbx
  int v20; // eax
  void *v21; // rbx
  unsigned int v22; // edi
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v26; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+54h] [rbp-ACh]
  GUID v28; // [rsp+58h] [rbp-A8h]
  GUID v29; // [rsp+68h] [rbp-98h]
  _BYTE v30[272]; // [rsp+78h] [rbp-88h] BYREF
  char v31; // [rsp+188h] [rbp+88h] BYREF
  struct IStream *v32; // [rsp+3A0h] [rbp+2A0h] BYREF
  WCHAR Dst[264]; // [rsp+3B0h] [rbp+2B0h] BYREF
  BYTE Data[2]; // [rsp+5C0h] [rbp+4C0h] BYREF

  hKey = 0;
  Type = 0;
  cbData[0] = 0;
  *(_WORD *)Data = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\DirectMusic", 0, 1u, &hKey) )
    goto LABEL_46;
  cbData[0] = 520;
  v2 = 260;
  v3 = 2147483646;
  v4 = RegQueryValueExW(hKey, L"GMFilePath", 0, &Type, Data, cbData);
  if ( v4 )
    goto LABEL_13;
  if ( Type != 2 )
  {
    if ( Type == 1 )
      goto LABEL_14;
    goto LABEL_13;
  }
  if ( !ExpandEnvironmentStringsW((LPCWSTR)Data, Dst, 0x104u) )
  {
LABEL_13:
    *(_WORD *)Data = 0;
    goto LABEL_14;
  }
  v5 = 2147483646;
  v6 = Dst;
  v7 = 260;
  v8 = Data;
  do
  {
    if ( !v5 )
      break;
    if ( !*v6 )
      break;
    *(_WORD *)v8 = *v6++;
    v8 += 2;
    --v5;
    --v7;
  }
  while ( v7 );
  v9 = v8 - 2;
  if ( v7 )
    v9 = v8;
  *(_WORD *)v9 = 0;
LABEL_14:
  RegCloseKey(hKey);
  if ( v4 )
    goto LABEL_46;
  memset_0(v30, 0, 0x330u);
  v26 = 856;
  v10 = Data;
  v11 = &v31;
  v29 = CLSID_DirectMusicCollection;
  do
  {
    if ( !v3 )
      break;
    if ( !*(_WORD *)v10 )
      break;
    *(_WORD *)v11 = *(_WORD *)v10;
    v10 += 2;
    v11 += 2;
    --v3;
    --v2;
  }
  while ( v2 );
  v12 = v11 - 2;
  if ( v2 )
    v12 = v11;
  *(_WORD *)v12 = 0;
  v28 = GUID_DefaultGMCollection;
  v27 = 51;
  CDescriptor::CDescriptor((CDescriptor *)Dst);
  if ( v26 >= 0x350 )
  {
    v13 = v27;
    v14 = 0;
    if ( (v27 & 0x800) == 0 )
    {
LABEL_28:
      if ( (v13 & 0x20) != 0 )
        v27 = v13 | 0x10;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
      hKey = 0;
      CDescriptor::Set((CDescriptor *)Dst, (struct _DMUS_OBJECTDESC *)&v26, v14);
      if ( (int)CLoader::GetClass(this, (struct CDescriptor *)Dst, (struct CClass **)&hKey, 1) >= 0 )
      {
        *(_QWORD *)cbData = 0;
        if ( (int)CClass::GetObjectA((CClass *)hKey, (struct CDescriptor *)Dst, (struct CObject **)cbData) >= 0 )
        {
          v16 = *(_DWORD **)cbData;
          if ( (Dst[4] & 0xC10) != 0 )
            *(_DWORD *)(*(_QWORD *)cbData + 16LL) &= 0xFFFFF3CF;
          CDescriptor::Merge((CDescriptor *)(v16 + 2), (struct CDescriptor *)Dst);
          if ( (v16[4] & 0xC10) != 0 )
          {
            if ( (v16[4] & 0x10) != 0 )
            {
              CObject::ParseFromFile((CObject *)v16);
            }
            else if ( (v16[4] & 0x400) != 0 )
            {
              CObject::ParseFromMemory((CObject *)v16);
            }
            else if ( (v16[4] & 0x800) != 0 )
            {
              CObject::ParseFromStream((CObject *)v16);
            }
          }
          CDescriptor::Get((CDescriptor *)(v16 + 2), (struct _DMUS_OBJECTDESC *)&v26);
        }
      }
      if ( v14 )
      {
        v27 |= 0x800u;
        ((void (__fastcall *)(struct IStream *))v32->lpVtbl->Release)(v32);
        v32 = v14;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
      goto LABEL_45;
    }
    v14 = v32;
    if ( v32 )
    {
      v15.lpVtbl = v32->lpVtbl;
      if ( v32->lpVtbl )
      {
        if ( v15.lpVtbl->QueryInterface
          && ((int (__fastcall *)(struct IStream *, struct IStream **))v15.lpVtbl->Clone)(v32, &v32) >= 0 )
        {
          v13 = v27;
          goto LABEL_28;
        }
      }
    }
  }
LABEL_45:
  CDescriptor::~CDescriptor((CDescriptor *)Dst);
LABEL_46:
  v17 = malloc(0xD8u);
  v18 = v17;
  if ( v17 )
  {
    *v17 = 0;
    CDescriptor::CDescriptor((CDescriptor *)(v17 + 1));
    *((_DWORD *)v18 + 48) = 0;
    v18[26] = 0;
    v18[23] = 0;
    v18[25] = 0;
  }
  else
  {
    v18 = 0;
  }
  *((_QWORD *)this + 77) = v18;
  if ( !v18 )
    return 2147942414LL;
  v20 = CObject::GC_Collectable((CObject *)v18);
  v21 = (void *)*((_QWORD *)this + 77);
  v22 = v20;
  if ( v20 >= 0 )
  {
    *((_QWORD *)this + 78) = v21;
    return 0;
  }
  else
  {
    if ( v21 )
    {
      CObject::~CObject(*((CObject **)this + 77));
      operator delete(v21, 0xD8u);
    }
    *((_QWORD *)this + 77) = 0;
    return v22;
  }
}

```

## disassembly

```asm
0x180008e90  mov     [rsp-8+arg_8], rbx
0x180008e95  mov     [rsp-8+arg_10], rsi
0x180008e9a  push    rbp
0x180008e9b  push    rdi
0x180008e9c  push    r12
0x180008e9e  push    r14
0x180008ea0  push    r15
0x180008ea2  lea     rbp, [rsp-6E0h]
0x180008eaa  sub     rsp, 7E0h
0x180008eb1  mov     rax, cs:__security_cookie
0x180008eb8  xor     rax, rsp
0x180008ebb  mov     [rbp+700h+var_30], rax
0x180008ec2  xor     r12d, r12d
0x180008ec5  lea     rax, [rsp+800h+hKey]
0x180008eca  mov     rsi, rcx
0x180008ecd  mov     [rsp+800h+hKey], r12
0x180008ed2  xor     r8d, r8d; ulOptions
0x180008ed5  mov     [rsp+800h+Type], r12d
0x180008eda  lea     rdx, SubKey; "Software\\Microsoft\\DirectMusic"
0x180008ee1  mov     [rsp+800h+cbData], r12d
0x180008ee6  lea     r9d, [r12+1]; samDesired
0x180008eeb  mov     word ptr [rbp+700h+Data], r12w
0x180008ef3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008efa  mov     [rsp+800h+phkResult], rax; phkResult
0x180008eff  call    cs:__imp_RegOpenKeyExW
0x180008f05  test    eax, eax
0x180008f07  jnz     loc_1800091E9
0x180008f0d  mov     rcx, [rsp+800h+hKey]; hKey
0x180008f12  lea     rax, [rsp+800h+cbData]
0x180008f17  mov     [rsp+800h+lpcbData], rax; lpcbData
0x180008f1c  lea     r9, [rsp+800h+Type]; lpType
0x180008f21  lea     rax, [rbp+700h+Data]
0x180008f28  mov     [rsp+800h+cbData], 208h
0x180008f30  xor     r8d, r8d; lpReserved
0x180008f33  mov     [rsp+800h+phkResult], rax; lpData
0x180008f38  lea     rdx, ValueName; "GMFilePath"
0x180008f3f  call    cs:__imp_RegQueryValueExW
0x180008f45  mov     ebx, 104h
0x180008f4a  mov     edi, 7FFFFFFEh
0x180008f4f  mov     r14d, eax
0x180008f52  test    eax, eax
0x180008f54  jnz     short loc_180008FC6
0x180008f56  cmp     [rsp+800h+Type], 2
0x180008f5b  jnz     short loc_180008FBF
0x180008f5d  mov     r8d, ebx; nSize
0x180008f60  lea     rdx, [rbp+700h+Dst]; lpDst
0x180008f67  lea     rcx, [rbp+700h+Data]; lpSrc
0x180008f6e  call    cs:__imp_ExpandEnvironmentStringsW
0x180008f74  test    eax, eax
0x180008f76  jz      short loc_180008FC6
0x180008f78  mov     ecx, edi
0x180008f7a  lea     r8, [rbp+700h+Dst]
0x180008f81  mov     edx, ebx
0x180008f83  lea     rax, [rbp+700h+Data]
0x180008f8a  test    rcx, rcx
0x180008f8d  jz      short loc_180008FAE
0x180008f8f  movzx   r9d, word ptr [r8]
0x180008f93  test    r9w, r9w
0x180008f97  jz      short loc_180008FAE
0x180008f99  mov     [rax], r9w
0x180008f9d  add     r8, 2
0x180008fa1  add     rax, 2
0x180008fa5  dec     rcx
0x180008fa8  sub     rdx, 1
0x180008fac  jnz     short loc_180008F8A
0x180008fae  test    rdx, rdx
0x180008fb1  lea     rcx, [rax-2]
0x180008fb5  cmovnz  rcx, rax
0x180008fb9  mov     [rcx], r12w
0x180008fbd  jmp     short loc_180008FCE
0x180008fbf  cmp     [rsp+800h+Type], 1
0x180008fc4  jz      short loc_180008FCE
0x180008fc6  mov     word ptr [rbp+700h+Data], r12w
0x180008fce  mov     rcx, [rsp+800h+hKey]; hKey
0x180008fd3  call    cs:__imp_RegCloseKey
0x180008fd9  test    r14d, r14d
0x180008fdc  jnz     loc_1800091E9
0x180008fe2  xor     edx, edx; Val
0x180008fe4  lea     rcx, [rsp+800h+var_788]; void *
0x180008fe9  mov     r8d, 330h; Size
0x180008fef  call    memset_0
0x180008ff4  movups  xmm0, xmmword ptr cs:CLSID_DirectMusicCollection.Data1
0x180008ffb  mov     [rsp+800h+var_7B0], 358h
0x180009003  lea     rcx, [rbp+700h+Data]
0x18000900a  lea     rax, [rbp+700h+var_678]
0x180009011  movdqu  [rsp+800h+var_798], xmm0
0x180009017  test    rdi, rdi
0x18000901a  jz      short loc_180009038
0x18000901c  movzx   edx, word ptr [rcx]
0x18000901f  test    dx, dx
0x180009022  jz      short loc_180009038
0x180009024  mov     [rax], dx
0x180009027  add     rcx, 2
0x18000902b  add     rax, 2
0x18000902f  dec     rdi
0x180009032  sub     rbx, 1
0x180009036  jnz     short loc_180009017
0x180009038  movups  xmm0, xmmword ptr cs:GUID_DefaultGMCollection.Data1
0x18000903f  lea     rcx, [rax-2]
0x180009043  test    rbx, rbx
0x180009046  cmovnz  rcx, rax
0x18000904a  mov     [rcx], r12w
0x18000904e  lea     rcx, [rbp+700h+Dst]; this
0x180009055  movdqu  [rsp+800h+var_7A8], xmm0
0x18000905b  mov     [rsp+800h+var_7AC], 33h ; '3'
0x180009063  call    ??0CDescriptor@@QEAA@XZ; CDescriptor::CDescriptor(void)
0x180009068  cmp     [rsp+800h+var_7B0], 350h
0x180009070  jb      loc_1800091DD
0x180009076  mov     eax, [rsp+800h+var_7AC]
0x18000907a  mov     rdi, r12
0x18000907d  bt      eax, 0Bh
0x180009081  jnb     short loc_1800090C7
0x180009083  mov     rdi, [rbp+700h+var_460]
0x18000908a  test    rdi, rdi
0x18000908d  jz      loc_1800091DD
0x180009093  mov     rax, [rdi]
0x180009096  test    rax, rax
0x180009099  jz      loc_1800091DD
0x18000909f  cmp     [rax], r12
0x1800090a2  jz      loc_1800091DD
0x1800090a8  mov     rax, [rax+68h]
0x1800090ac  lea     rdx, [rbp+700h+var_460]
0x1800090b3  mov     rcx, rdi
0x1800090b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090bb  test    eax, eax
0x1800090bd  js      loc_1800091DD
0x1800090c3  mov     eax, [rsp+800h+var_7AC]
0x1800090c7  test    al, 20h
0x1800090c9  jz      short loc_1800090D2
0x1800090cb  or      eax, 10h
0x1800090ce  mov     [rsp+800h+var_7AC], eax
0x1800090d2  lea     r15, [rsi+238h]
0x1800090d9  mov     rcx, r15; lpCriticalSection
0x1800090dc  call    cs:__imp_EnterCriticalSection
0x1800090e2  mov     r8, rdi; struct IStream *
0x1800090e5  mov     [rsp+800h+hKey], r12
0x1800090ea  lea     rdx, [rsp+800h+var_7B0]; struct _DMUS_OBJECTDESC *
0x1800090ef  lea     rcx, [rbp+700h+Dst]; this
0x1800090f6  call    ?Set@CDescriptor@@QEAAXPEAU_DMUS_OBJECTDESC@@PEAUIStream@@@Z; CDescriptor::Set(_DMUS_OBJECTDESC *,IStream *)
0x1800090fb  mov     r9d, 1; int
0x180009101  lea     r8, [rsp+800h+hKey]; struct CClass **
0x180009106  lea     rdx, [rbp+700h+Dst]; struct CDescriptor *
0x18000910d  mov     rcx, rsi; this
0x180009110  call    ?GetClass@CLoader@@AEAAJPEAVCDescriptor@@PEAPEAVCClass@@H@Z; CLoader::GetClass(CDescriptor *,CClass * *,int)
0x180009115  test    eax, eax
0x180009117  js      loc_1800091AF
0x18000911d  mov     rcx, [rsp+800h+hKey]; this
0x180009122  lea     r8, [rsp+800h+cbData]; struct CObject **
0x180009127  lea     rdx, [rbp+700h+Dst]; struct CDescriptor *
0x18000912e  mov     qword ptr [rsp+800h+cbData], r12
0x180009133  call    ?GetObjectA@CClass@@QEAAJPEAVCDescriptor@@PEAPEAVCObject@@@Z; CClass::GetObjectA(CDescriptor *,CObject * *)
0x180009138  test    eax, eax
0x18000913a  js      short loc_1800091AF
0x18000913c  test    [rbp+700h+var_448], 0C10h
0x180009146  mov     rbx, qword ptr [rsp+800h+cbData]
0x18000914b  jz      short loc_180009154
0x18000914d  and     dword ptr [rbx+10h], 0FFFFF3CFh
0x180009154  lea     rdx, [rbp+700h+Dst]; struct CDescriptor *
0x18000915b  lea     rcx, [rbx+8]; this
0x18000915f  call    ?Merge@CDescriptor@@QEAAXPEAV1@@Z; CDescriptor::Merge(CDescriptor *)
0x180009164  test    dword ptr [rbx+10h], 0C10h
0x18000916b  jz      short loc_1800091A1
0x18000916d  test    byte ptr [rbx+10h], 10h
0x180009171  jz      short loc_18000917D
0x180009173  mov     rcx, rbx; this
0x180009176  call    ?ParseFromFile@CObject@@QEAAJXZ; CObject::ParseFromFile(void)
0x18000917b  jmp     short loc_1800091A1
0x18000917d  test    dword ptr [rbx+10h], 400h
0x180009184  jz      short loc_180009190
0x180009186  mov     rcx, rbx; this
0x180009189  call    ?ParseFromMemory@CObject@@QEAAJXZ; CObject::ParseFromMemory(void)
0x18000918e  jmp     short loc_1800091A1
0x180009190  test    dword ptr [rbx+10h], 800h
0x180009197  jz      short loc_1800091A1
0x180009199  mov     rcx, rbx; this
0x18000919c  call    ?ParseFromStream@CObject@@QEAAJXZ; CObject::ParseFromStream(void)
0x1800091a1  lea     rdx, [rsp+800h+var_7B0]; struct _DMUS_OBJECTDESC *
0x1800091a6  lea     rcx, [rbx+8]; this
0x1800091aa  call    ?Get@CDescriptor@@QEAAXPEAU_DMUS_OBJECTDESC@@@Z; CDescriptor::Get(_DMUS_OBJECTDESC *)
0x1800091af  test    rdi, rdi
0x1800091b2  jz      short loc_1800091D4
0x1800091b4  mov     rcx, [rbp+700h+var_460]
0x1800091bb  bts     [rsp+800h+var_7AC], 0Bh
0x1800091c1  mov     rax, [rcx]
0x1800091c4  mov     rax, [rax+10h]
0x1800091c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091cd  mov     [rbp+700h+var_460], rdi
0x1800091d4  mov     rcx, r15; lpCriticalSection
0x1800091d7  call    cs:__imp_LeaveCriticalSection
0x1800091dd  lea     rcx, [rbp+700h+Dst]; this
0x1800091e4  call    ??1CDescriptor@@QEAA@XZ; CDescriptor::~CDescriptor(void)
0x1800091e9  mov     r14d, 0D8h
0x1800091ef  mov     ecx, r14d; Size
0x1800091f2  call    cs:__imp_malloc
0x1800091f8  mov     rbx, rax
0x1800091fb  test    rax, rax
0x1800091fe  jz      short loc_18000922A
0x180009200  lea     rcx, [rax+8]; this
0x180009204  mov     [rax], r12
0x180009207  call    ??0CDescriptor@@QEAA@XZ; CDescriptor::CDescriptor(void)
0x18000920c  mov     [rbx+0C0h], r12d
0x180009213  mov     [rbx+0D0h], r12
0x18000921a  mov     [rbx+0B8h], r12
0x180009221  mov     [rbx+0C8h], r12
0x180009228  jmp     short loc_18000922D
0x18000922a  mov     rbx, r12
0x18000922d  mov     [rsi+268h], rbx
0x180009234  test    rbx, rbx
0x180009237  jnz     short loc_180009240
0x180009239  mov     eax, 8007000Eh
0x18000923e  jmp     short loc_180009281
0x180009240  mov     rcx, rbx; this
0x180009243  call    ?GC_Collectable@CObject@@QEAAJXZ; CObject::GC_Collectable(void)
0x180009248  mov     rbx, [rsi+268h]
0x18000924f  mov     edi, eax
0x180009251  test    eax, eax
0x180009253  jns     short loc_180009278
0x180009255  test    rbx, rbx
0x180009258  jz      short loc_18000926D
0x18000925a  mov     rcx, rbx; this
0x18000925d  call    ??1CObject@@QEAA@XZ; CObject::~CObject(void)
0x180009262  mov     rdx, r14; unsigned __int64
0x180009265  mov     rcx, rbx; void *
0x180009268  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000926d  mov     [rsi+268h], r12
0x180009274  mov     eax, edi
0x180009276  jmp     short loc_180009281
0x180009278  mov     [rsi+270h], rbx
0x18000927f  xor     eax, eax
0x180009281  mov     rcx, [rbp+700h+var_30]
0x180009288  xor     rcx, rsp; StackCookie
0x18000928b  call    __security_check_cookie
0x180009290  lea     r11, [rsp+800h+var_20]
0x180009298  mov     rbx, [r11+38h]
0x18000929c  mov     rsi, [r11+40h]
0x1800092a0  mov     rsp, r11
0x1800092a3  pop     r15
0x1800092a5  pop     r14
0x1800092a7  pop     r12
0x1800092a9  pop     rdi
0x1800092aa  pop     rbp
0x1800092ab  retn
```
