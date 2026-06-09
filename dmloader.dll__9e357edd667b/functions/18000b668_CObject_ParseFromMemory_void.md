# CObject::ParseFromMemory(void)

- ea: `0x18000b668`
- end: `0x18000b813`
- name: `?ParseFromMemory@CObject@@QEAAJXZ`
- size: `427`
- prototype: `__int64 __fastcall(CObject *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180008e90`
- `0x180009b20`

## callees

- `0x1800015d0`
- `0x180001ef0`
- `0x180009fdc`
- `0x18000a10c`
- `0x18000b358`
- `0x18000b668`
- `0x18000c018`
- `0x18000dba0`
- `0x180010010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b6d6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b6d6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b6c2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b6c2`

## pseudocode

```c
__int64 __fastcall CObject::ParseFromMemory(CObject *this)
{
  HRESULT v2; // edi
  _QWORD *v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v9[176]; // [rsp+40h] [rbp-C0h] BYREF
  int v10; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v11[860]; // [rsp+F4h] [rbp-Ch] BYREF

  ppv = 0;
  v2 = CoCreateInstance((const IID *const)((char *)this + 36), 0, 1u, &IID_IDirectMusicObject, &ppv);
  if ( v2 >= 0 )
  {
    v3 = malloc(0x38u);
    if ( v3 )
    {
      v4 = *(_QWORD *)(*((_QWORD *)this + 26) + 184LL);
      *v3 = &CMemStream::`vftable'{for `IStream'};
      v3[1] = &CMemStream::`vftable'{for `IDirectMusicGetLoader'};
      *((_DWORD *)v3 + 4) = 1;
      v3[3] = 0;
      v3[4] = 0;
      v3[5] = 0;
      v3[6] = v4;
      if ( v4 )
        _InterlockedAdd((volatile signed __int32 *)(v4 + 560), 1u);
      v5 = *((_QWORD *)this + 13);
      v6 = *((_QWORD *)this + 1);
      v3[3] = v5;
      v3[4] = v6;
      v3[5] = 0;
      if ( v5 && v6 )
      {
        memset_0(v11, 0, 0x354u);
        v10 = 856;
        v2 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *, int *))(*(_QWORD *)ppv + 40LL))(ppv, v3, &v10);
        if ( v2 >= 0 )
        {
          CDescriptor::CDescriptor((CDescriptor *)v9);
          CDescriptor::Set((CDescriptor *)v9, (struct _DMUS_OBJECTDESC *)&v10, 0);
          CDescriptor::Merge((CObject *)((char *)this + 8), (struct CDescriptor *)v9);
          CDescriptor::~CDescriptor((CDescriptor *)v9);
        }
      }
      else
      {
        v2 = -2005397118;
      }
      CMemStream::Release((CMemStream *)v3);
    }
    else
    {
      v2 = -2147024882;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000b668  mov     [rsp-8+arg_8], rbx
0x18000b66d  mov     [rsp-8+arg_10], rsi
0x18000b672  push    rbp
0x18000b673  push    rdi
0x18000b674  push    r14
0x18000b676  lea     rbp, [rsp-360h]
0x18000b67e  sub     rsp, 460h
0x18000b685  mov     rax, cs:__security_cookie
0x18000b68c  xor     rax, rsp
0x18000b68f  mov     [rbp+370h+var_20], rax
0x18000b696  mov     rsi, rcx
0x18000b699  mov     [rsp+470h+var_440], 0
0x18000b6a2  lea     rax, [rsp+470h+var_440]
0x18000b6a7  mov     r14d, 1
0x18000b6ad  mov     r8d, r14d; dwClsContext
0x18000b6b0  mov     [rsp+470h+ppv], rax; ppv
0x18000b6b5  add     rcx, 24h ; '$'; rclsid
0x18000b6b9  lea     r9, IID_IDirectMusicObject; riid
0x18000b6c0  xor     edx, edx; pUnkOuter
0x18000b6c2  call    cs:__imp_CoCreateInstance
0x18000b6c8  mov     edi, eax
0x18000b6ca  test    eax, eax
0x18000b6cc  js      loc_18000B7EA
0x18000b6d2  lea     ecx, [r14+37h]; Size
0x18000b6d6  call    cs:__imp_malloc
0x18000b6dc  mov     rbx, rax
0x18000b6df  test    rax, rax
0x18000b6e2  jz      loc_18000B7D4
0x18000b6e8  mov     rcx, [rsi+0D0h]
0x18000b6ef  mov     rax, [rcx+0B8h]
0x18000b6f6  lea     rcx, ??_7CMemStream@@6BIStream@@@; const CMemStream::`vftable'{for `IStream'}
0x18000b6fd  mov     [rbx], rcx
0x18000b700  lea     rcx, ??_7CMemStream@@6BIDirectMusicGetLoader@@@; const CMemStream::`vftable'{for `IDirectMusicGetLoader'}
0x18000b707  mov     [rbx+8], rcx
0x18000b70b  mov     [rbx+10h], r14d
0x18000b70f  mov     qword ptr [rbx+18h], 0
0x18000b717  mov     qword ptr [rbx+20h], 0
0x18000b71f  mov     qword ptr [rbx+28h], 0
0x18000b727  mov     [rbx+30h], rax
0x18000b72b  test    rax, rax
0x18000b72e  jz      short loc_18000B738
0x18000b730  lock add [rax+230h], r14d
0x18000b738  mov     rax, [rsi+68h]
0x18000b73c  mov     rcx, [rsi+8]
0x18000b740  mov     [rbx+18h], rax
0x18000b744  mov     [rbx+20h], rcx
0x18000b748  mov     qword ptr [rbx+28h], 0
0x18000b750  test    rax, rax
0x18000b753  jz      short loc_18000B7C5
0x18000b755  test    rcx, rcx
0x18000b758  jz      short loc_18000B7C5
0x18000b75a  xor     edx, edx; Val
0x18000b75c  lea     rcx, [rbp+370h+var_37C]; void *
0x18000b760  mov     r8d, 354h; Size
0x18000b766  call    memset_0
0x18000b76b  mov     rcx, [rsp+470h+var_440]
0x18000b770  lea     r8, [rbp+370h+var_380]
0x18000b774  mov     [rbp+370h+var_380], 358h
0x18000b77b  mov     rdx, rbx
0x18000b77e  mov     rax, [rcx]
0x18000b781  mov     rax, [rax+28h]
0x18000b785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b78a  mov     edi, eax
0x18000b78c  test    eax, eax
0x18000b78e  js      short loc_18000B7CA
0x18000b790  lea     rcx, [rsp+470h+var_430]; this
0x18000b795  call    ??0CDescriptor@@QEAA@XZ; CDescriptor::CDescriptor(void)
0x18000b79a  xor     r8d, r8d; struct IStream *
0x18000b79d  lea     rdx, [rbp+370h+var_380]; struct _DMUS_OBJECTDESC *
0x18000b7a1  lea     rcx, [rsp+470h+var_430]; this
0x18000b7a6  call    ?Set@CDescriptor@@QEAAXPEAU_DMUS_OBJECTDESC@@PEAUIStream@@@Z; CDescriptor::Set(_DMUS_OBJECTDESC *,IStream *)
0x18000b7ab  lea     rdx, [rsp+470h+var_430]; struct CDescriptor *
0x18000b7b0  lea     rcx, [rsi+8]; this
0x18000b7b4  call    ?Merge@CDescriptor@@QEAAXPEAV1@@Z; CDescriptor::Merge(CDescriptor *)
0x18000b7b9  lea     rcx, [rsp+470h+var_430]; this
0x18000b7be  call    ??1CDescriptor@@QEAA@XZ; CDescriptor::~CDescriptor(void)
0x18000b7c3  jmp     short loc_18000B7CA
0x18000b7c5  mov     edi, 88781182h
0x18000b7ca  mov     rcx, rbx; this
0x18000b7cd  call    ?Release@CMemStream@@UEAAKXZ; CMemStream::Release(void)
0x18000b7d2  jmp     short loc_18000B7D9
0x18000b7d4  mov     edi, 8007000Eh
0x18000b7d9  mov     rcx, [rsp+470h+var_440]
0x18000b7de  mov     rax, [rcx]
0x18000b7e1  mov     rax, [rax+10h]
0x18000b7e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7ea  mov     eax, edi
0x18000b7ec  mov     rcx, [rbp+370h+var_20]
0x18000b7f3  xor     rcx, rsp; StackCookie
0x18000b7f6  call    __security_check_cookie
0x18000b7fb  lea     r11, [rsp+470h+var_10]
0x18000b803  mov     rbx, [r11+28h]
0x18000b807  mov     rsi, [r11+30h]
0x18000b80b  mov     rsp, r11
0x18000b80e  pop     r14
0x18000b810  pop     rdi
0x18000b811  pop     rbp
0x18000b812  retn
```
