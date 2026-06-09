# StoreAppUserBlob::GetContent(tagBLOB const *,wchar_t * *,IStream * *)

- ea: `0x18000c3e4`
- end: `0x18000c555`
- name: `?GetContent@StoreAppUserBlob@@YAJPEBUtagBLOB@@PEAPEA_WPEAPEAUIStream@@@Z`
- size: `369`
- prototype: `__int64 __fastcall(StoreAppUserBlob *this, const struct tagBLOB *, LPVOID *, struct IStream **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022cc8`

## callees

- `0x18000ba60`
- `0x18000c3e4`
- `0x18000e050`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c531`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c531`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x18000c50d`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x18000c50d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c493`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c493`
- `SHCORE!SHCreateMemStream` at `0x18000c4cf`
- `SHCORE!SHCreateMemStream` at `0x18000c4cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StoreAppUserBlob::GetContent(
        StoreAppUserBlob *this,
        const struct tagBLOB *a2,
        LPVOID *a3,
        struct IStream **a4)
{
  _DWORD *v6; // rsi
  unsigned int v7; // r12d
  unsigned int v8; // ebp
  unsigned int v9; // eax
  int v10; // edi
  unsigned int v11; // ecx
  int v12; // edx
  unsigned int v13; // ecx
  bool v14; // cf
  unsigned int v15; // eax
  wchar_t *v16; // rax
  wchar_t *v17; // r14
  wchar_t *v18; // rbx
  IStream *v19; // rax
  IStream *v20; // rdi
  IStream *v22; // [rsp+60h] [rbp+8h] BYREF
  LPVOID *ppv; // [rsp+70h] [rbp+18h]

  ppv = a3;
  *(_QWORD *)&a2->cbSize = 0;
  *a3 = 0;
  v6 = (_DWORD *)*((_QWORD *)this + 1);
  v7 = 0;
  v8 = 0;
  v9 = v6[1];
  v10 = -2147024362;
  if ( (*v6 & 1) != 0 )
  {
    v11 = v9 + 16;
    if ( v9 >= 0xFFFFFFF0 )
    {
      v12 = -1;
      goto LABEL_11;
    }
    v8 = v11 + v6[2];
    if ( v8 < v11 )
      return (unsigned int)v10;
    v7 = v9 + 16;
    v13 = v8 + v6[3];
    v12 = -1;
    v14 = v13 < v8;
    if ( v13 >= v8 )
      v12 = v8 + v6[3];
  }
  else
  {
    v15 = v9 + 8;
    v12 = -1;
    v14 = v15 < 8;
    if ( v15 >= 8 )
      v12 = v15;
  }
  v10 = v14 ? 0x80070216 : 0;
LABEL_11:
  if ( v10 >= 0 )
  {
    if ( v12 != *(_DWORD *)this )
      return (unsigned int)-2147024809;
    if ( (*v6 & 1) == 0 )
      return 1;
    if ( v7 && v8 )
    {
      v16 = (wchar_t *)CoTaskMemAlloc((unsigned int)v6[2]);
      v17 = v16;
      if ( v16 )
      {
        v18 = v16;
        v10 = StringCbCopyW(v16, (unsigned int)v6[2], (const wchar_t *)(*((_QWORD *)this + 1) + v7));
        if ( v10 < 0 )
          goto LABEL_27;
        v19 = SHCreateMemStream((const BYTE *)(*((_QWORD *)this + 1) + v8), v6[3]);
        v20 = v19;
        v22 = v19;
        if ( v19 )
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)v19 + 8LL))(v19);
        if ( v20 )
        {
          v10 = CoUnmarshalInterface(v20, &GUID_0000000c_0000_0000_c000_000000000046, ppv);
          if ( v10 >= 0 )
          {
            v18 = 0;
            *(_QWORD *)&a2->cbSize = v17;
          }
        }
        else
        {
          v10 = -2147024882;
        }
        Microsoft::WRL::ComPtr<IStream>::InternalRelease(&v22);
        if ( v18 )
LABEL_27:
          CoTaskMemFree(v18);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000c3e4  mov     [rsp+arg_8], rbx
0x18000c3e9  mov     [rsp+ppv], r8
0x18000c3ee  push    rbp
0x18000c3ef  push    rsi
0x18000c3f0  push    rdi
0x18000c3f1  push    r12
0x18000c3f3  push    r13
0x18000c3f5  push    r14
0x18000c3f7  push    r15
0x18000c3f9  sub     rsp, 20h
0x18000c3fd  mov     r13, rdx
0x18000c400  mov     r15, rcx
0x18000c403  mov     qword ptr [rdx], 0
0x18000c40a  mov     qword ptr [r8], 0
0x18000c411  mov     rsi, [rcx+8]
0x18000c415  xor     r12d, r12d
0x18000c418  xor     ebp, ebp
0x18000c41a  mov     r9d, [rsi]
0x18000c41d  and     r9d, 1
0x18000c421  mov     eax, [rsi+4]
0x18000c424  mov     edi, 80070216h
0x18000c429  jz      short loc_18000C457
0x18000c42b  lea     ecx, [rax+10h]
0x18000c42e  cmp     ecx, 10h
0x18000c431  jnb     short loc_18000C438
0x18000c433  or      edx, 0FFFFFFFFh
0x18000c436  jmp     short loc_18000C467
0x18000c438  mov     ebp, [rsi+8]
0x18000c43b  add     ebp, ecx
0x18000c43d  cmp     ebp, ecx
0x18000c43f  jb      loc_18000C53E
0x18000c445  mov     r12d, ecx
0x18000c448  mov     ecx, [rsi+0Ch]
0x18000c44b  add     ecx, ebp
0x18000c44d  or      edx, 0FFFFFFFFh
0x18000c450  cmp     ecx, ebp
0x18000c452  cmovnb  edx, ecx
0x18000c455  jmp     short loc_18000C463
0x18000c457  add     eax, 8
0x18000c45a  or      edx, 0FFFFFFFFh
0x18000c45d  cmp     eax, 8
0x18000c460  cmovnb  edx, eax
0x18000c463  sbb     eax, eax
0x18000c465  and     edi, eax
0x18000c467  test    edi, edi
0x18000c469  js      loc_18000C53E
0x18000c46f  cmp     edx, [r15]
0x18000c472  jz      short loc_18000C47E
0x18000c474  mov     edi, 80070057h
0x18000c479  jmp     loc_18000C53E
0x18000c47e  test    r9d, r9d
0x18000c481  jz      loc_18000C539
0x18000c487  test    r12d, r12d
0x18000c48a  jz      short loc_18000C474
0x18000c48c  test    ebp, ebp
0x18000c48e  jz      short loc_18000C474
0x18000c490  mov     ecx, [rsi+8]; cb
0x18000c493  call    cs:__imp_CoTaskMemAlloc
0x18000c499  mov     r14, rax
0x18000c49c  test    rax, rax
0x18000c49f  jnz     short loc_18000C4AB
0x18000c4a1  mov     edi, 8007000Eh
0x18000c4a6  jmp     loc_18000C53E
0x18000c4ab  mov     rbx, r14
0x18000c4ae  mov     r8d, r12d
0x18000c4b1  add     r8, [r15+8]; wchar_t *
0x18000c4b5  mov     edx, [rsi+8]; unsigned __int64
0x18000c4b8  mov     rcx, r14; wchar_t *
0x18000c4bb  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000c4c0  mov     edi, eax
0x18000c4c2  test    eax, eax
0x18000c4c4  js      short loc_18000C52E
0x18000c4c6  mov     ecx, ebp
0x18000c4c8  add     rcx, [r15+8]; pInit
0x18000c4cc  mov     edx, [rsi+0Ch]; cbInit
0x18000c4cf  call    cs:__imp_SHCreateMemStream
0x18000c4d5  mov     rdi, rax
0x18000c4d8  mov     [rsp+58h+arg_0], rax
0x18000c4dd  test    rax, rax
0x18000c4e0  jz      short loc_18000C4F2
0x18000c4e2  mov     rax, [rax]
0x18000c4e5  mov     rcx, rdi
0x18000c4e8  mov     rax, [rax+8]
0x18000c4ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4f1  nop
0x18000c4f2  test    rdi, rdi
0x18000c4f5  jnz     short loc_18000C4FE
0x18000c4f7  mov     edi, 8007000Eh
0x18000c4fc  jmp     short loc_18000C51F
0x18000c4fe  mov     r8, [rsp+58h+ppv]; ppv
0x18000c503  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046; riid
0x18000c50a  mov     rcx, rdi; pStm
0x18000c50d  call    cs:__imp_CoUnmarshalInterface
0x18000c513  mov     edi, eax
0x18000c515  test    eax, eax
0x18000c517  js      short loc_18000C51F
0x18000c519  xor     ebx, ebx
0x18000c51b  mov     [r13+0], r14
0x18000c51f  lea     rcx, [rsp+58h+arg_0]
0x18000c524  call    ?InternalRelease@?$ComPtr@UIStream@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IStream>::InternalRelease(void)
0x18000c529  test    rbx, rbx
0x18000c52c  jz      short loc_18000C53E
0x18000c52e  mov     rcx, rbx; pv
0x18000c531  call    cs:__imp_CoTaskMemFree
0x18000c537  jmp     short loc_18000C53E
0x18000c539  mov     edi, 1
0x18000c53e  mov     eax, edi
0x18000c540  mov     rbx, [rsp+58h+arg_8]
0x18000c545  add     rsp, 20h
0x18000c549  pop     r15
0x18000c54b  pop     r14
0x18000c54d  pop     r13
0x18000c54f  pop     r12
0x18000c551  pop     rdi
0x18000c552  pop     rsi
0x18000c553  pop     rbp
0x18000c554  retn
```
