# CMDCOM::ComMDSaveData(ulong)

- ea: `0x180019b60`
- end: `0x180019c54`
- name: `?ComMDSaveData@CMDCOM@@UEAAJK@Z`
- size: `244`
- prototype: `int(CMDCOM *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180019b60`
- `0x18001f638`
- `0x180023548`
- `0x180028f34`
- `0x180031010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180019c39`
- `ole32!CoTaskMemFree` at `0x180019c39`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDSaveData(CMDCOM *this, unsigned int a2)
{
  int v4; // ebx
  int inited; // eax
  __int64 v6; // rcx
  _BYTE *v7; // rdi
  _QWORD v9[2]; // [rsp+40h] [rbp-58h] BYREF
  int v10; // [rsp+50h] [rbp-48h]
  __int128 v11; // [rsp+58h] [rbp-40h]
  __int64 v12; // [rsp+68h] [rbp-30h]
  LPVOID pv; // [rsp+B0h] [rbp+18h] BYREF

  v9[1] = 0;
  v10 = 0;
  v11 = 0;
  v9[0] = &IIS_CRYPTO_STORAGE::`vftable';
  v12 = 0;
  pv = 0;
  if ( g_dwInitialized )
  {
    inited = InitStorageAndSessionKey((struct IIS_CRYPTO_STORAGE *)v9, (struct _IIS_CRYPTO_BLOB **)&pv);
    v7 = pv;
    v4 = inited;
    if ( inited >= 0 )
    {
      v4 = SaveAllData(v6, (struct IIS_CRYPTO_STORAGE *)v9, (struct _IIS_CRYPTO_BLOB *)pv, 0, 0, a2, 0, 0);
      if ( v4 >= 0 )
      {
        if ( !dword_180048764 || (v4 = (*(__int64 (__fastcall **)(CMDCOM *))(*(_QWORD *)this + 528LL))(this), v4 >= 0) )
          v4 = 0;
      }
    }
    if ( v7 )
    {
      *v7 = 88;
      CoTaskMemFree(v7);
    }
  }
  else
  {
    v4 = -2146646016;
  }
  IIS_CRYPTO_STORAGE::~IIS_CRYPTO_STORAGE((IIS_CRYPTO_STORAGE *)v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180019b60  mov     r11, rsp
0x180019b63  push    rbx
0x180019b64  push    rbp
0x180019b65  push    rsi
0x180019b66  push    rdi
0x180019b67  sub     rsp, 78h
0x180019b6b  mov     qword ptr [r11-50h], 0
0x180019b73  lea     rax, ??_7IIS_CRYPTO_STORAGE@@6B@; const IIS_CRYPTO_STORAGE::`vftable'
0x180019b7a  mov     [rsp+98h+var_48], 0
0x180019b82  xorps   xmm0, xmm0
0x180019b85  movdqu  [rsp+98h+var_40], xmm0
0x180019b8b  mov     [r11-58h], rax
0x180019b8f  mov     ebp, edx
0x180019b91  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180019b97  mov     rsi, rcx
0x180019b9a  mov     qword ptr [r11-30h], 0
0x180019ba2  mov     qword ptr [r11+18h], 0
0x180019baa  test    eax, eax
0x180019bac  jnz     short loc_180019BB8
0x180019bae  mov     ebx, 800CC800h
0x180019bb3  jmp     loc_180019C3F
0x180019bb8  lea     rdx, [rsp+98h+pv]; struct _IIS_CRYPTO_BLOB **
0x180019bc0  lea     rcx, [rsp+98h+var_58]; this
0x180019bc5  call    ?InitStorageAndSessionKey@@YAJPEAVIIS_CRYPTO_STORAGE@@PEAPEFAU_IIS_CRYPTO_BLOB@@@Z; InitStorageAndSessionKey(IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB * *)
0x180019bca  mov     rdi, [rsp+98h+pv]
0x180019bd2  mov     ebx, eax
0x180019bd4  test    eax, eax
0x180019bd6  js      short loc_180019C2E
0x180019bd8  mov     [rsp+98h+var_60], 0; int
0x180019be0  lea     rdx, [rsp+98h+var_58]; struct IIS_CRYPTO_STORAGE *
0x180019be5  mov     [rsp+98h+var_68], 0; int
0x180019bed  xor     r9d, r9d; unsigned __int16 *
0x180019bf0  mov     [rsp+98h+var_70], ebp; unsigned int
0x180019bf4  mov     r8, rdi; struct _IIS_CRYPTO_BLOB *
0x180019bf7  mov     [rsp+98h+var_78], 0; unsigned __int16 *
0x180019c00  call    ?SaveAllData@@YAJHPEAVIIS_CRYPTO_STORAGE@@PEFAU_IIS_CRYPTO_BLOB@@PEAG2KHH@Z; SaveAllData(int,IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB *,ushort *,ushort *,ulong,int,int)
0x180019c05  mov     ebx, eax
0x180019c07  test    eax, eax
0x180019c09  js      short loc_180019C2E
0x180019c0b  cmp     cs:dword_180048764, 0
0x180019c12  jz      short loc_180019C2C
0x180019c14  mov     rax, [rsi]
0x180019c17  mov     rcx, rsi
0x180019c1a  mov     rax, [rax+210h]
0x180019c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c26  mov     ebx, eax
0x180019c28  test    eax, eax
0x180019c2a  js      short loc_180019C2E
0x180019c2c  xor     ebx, ebx
0x180019c2e  test    rdi, rdi
0x180019c31  jz      short loc_180019C3F
0x180019c33  mov     rcx, rdi; pv
0x180019c36  mov     byte ptr [rdi], 58h ; 'X'
0x180019c39  call    cs:__imp_CoTaskMemFree
0x180019c3f  lea     rcx, [rsp+98h+var_58]; this
0x180019c44  call    ??1IIS_CRYPTO_STORAGE@@QEAA@XZ; IIS_CRYPTO_STORAGE::~IIS_CRYPTO_STORAGE(void)
0x180019c49  mov     eax, ebx
0x180019c4b  add     rsp, 78h
0x180019c4f  pop     rdi
0x180019c50  pop     rsi
0x180019c51  pop     rbp
0x180019c52  pop     rbx
0x180019c53  retn
```
