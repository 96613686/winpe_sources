# CObject::ParseFromStream(void)

- ea: `0x18000b81c`
- end: `0x18000b9a7`
- name: `?ParseFromStream@CObject@@QEAAJXZ`
- size: `395`
- prototype: `__int64 __fastcall(CObject *__hidden this)`
- caller_count: `2`
- callee_count: `10`
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
- `0x18000b81c`
- `0x18000c018`
- `0x18000d8e0`
- `0x18000dc50`
- `0x180010010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b88a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b88a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b876`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b876`

## pseudocode

```c
__int64 __fastcall CObject::ParseFromStream(CObject *this)
{
  HRESULT v2; // edi
  _QWORD *v3; // rbx
  __int64 v4; // rax
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v7[176]; // [rsp+40h] [rbp-C0h] BYREF
  int v8; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v9[860]; // [rsp+F4h] [rbp-Ch] BYREF

  ppv = 0;
  v2 = CoCreateInstance((const IID *const)((char *)this + 36), 0, 1u, &IID_IDirectMusicObject, &ppv);
  if ( v2 >= 0 )
  {
    v3 = malloc(0x28u);
    if ( v3 )
    {
      v4 = *(_QWORD *)(*((_QWORD *)this + 26) + 184LL);
      *v3 = &CStream::`vftable'{for `IStream'};
      v3[1] = &CStream::`vftable'{for `IDirectMusicGetLoader'};
      *((_DWORD *)v3 + 4) = 1;
      v3[3] = 0;
      v3[4] = v4;
      if ( v4 )
        _InterlockedAdd((volatile signed __int32 *)(v4 + 560), 1u);
      v2 = CStream::Open((CStream *)v3, *((struct IStream **)this + 14), *(union _LARGE_INTEGER *)((char *)this + 128));
      if ( v2 >= 0 )
      {
        memset_0(v9, 0, 0x354u);
        v8 = 856;
        v2 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *, int *))(*(_QWORD *)ppv + 40LL))(ppv, v3, &v8);
        if ( v2 >= 0 )
        {
          CDescriptor::CDescriptor((CDescriptor *)v7);
          CDescriptor::Set((CDescriptor *)v7, (struct _DMUS_OBJECTDESC *)&v8, 0);
          CDescriptor::Merge((CObject *)((char *)this + 8), (struct CDescriptor *)v7);
          CDescriptor::~CDescriptor((CDescriptor *)v7);
        }
      }
      CStream::Release((CStream *)v3);
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
0x18000b81c  mov     [rsp-8+arg_8], rbx
0x18000b821  mov     [rsp-8+arg_10], rsi
0x18000b826  push    rbp
0x18000b827  push    rdi
0x18000b828  push    r14
0x18000b82a  lea     rbp, [rsp-360h]
0x18000b832  sub     rsp, 460h
0x18000b839  mov     rax, cs:__security_cookie
0x18000b840  xor     rax, rsp
0x18000b843  mov     [rbp+370h+var_20], rax
0x18000b84a  mov     rsi, rcx
0x18000b84d  mov     [rsp+470h+var_440], 0
0x18000b856  lea     rax, [rsp+470h+var_440]
0x18000b85b  mov     r14d, 1
0x18000b861  mov     r8d, r14d; dwClsContext
0x18000b864  mov     [rsp+470h+ppv], rax; ppv
0x18000b869  add     rcx, 24h ; '$'; rclsid
0x18000b86d  lea     r9, IID_IDirectMusicObject; riid
0x18000b874  xor     edx, edx; pUnkOuter
0x18000b876  call    cs:__imp_CoCreateInstance
0x18000b87c  mov     edi, eax
0x18000b87e  test    eax, eax
0x18000b880  js      loc_18000B97E
0x18000b886  lea     ecx, [r14+27h]; Size
0x18000b88a  call    cs:__imp_malloc
0x18000b890  mov     rbx, rax
0x18000b893  test    rax, rax
0x18000b896  jz      loc_18000B968
0x18000b89c  mov     rcx, [rsi+0D0h]
0x18000b8a3  mov     rax, [rcx+0B8h]
0x18000b8aa  lea     rcx, ??_7CStream@@6BIStream@@@; const CStream::`vftable'{for `IStream'}
0x18000b8b1  mov     [rbx], rcx
0x18000b8b4  lea     rcx, ??_7CStream@@6BIDirectMusicGetLoader@@@; const CStream::`vftable'{for `IDirectMusicGetLoader'}
0x18000b8bb  mov     [rbx+8], rcx
0x18000b8bf  mov     [rbx+10h], r14d
0x18000b8c3  mov     qword ptr [rbx+18h], 0
0x18000b8cb  mov     [rbx+20h], rax
0x18000b8cf  test    rax, rax
0x18000b8d2  jz      short loc_18000B8DC
0x18000b8d4  lock add [rax+230h], r14d
0x18000b8dc  mov     r8, [rsi+80h]; union _LARGE_INTEGER
0x18000b8e3  mov     rcx, rbx; this
0x18000b8e6  mov     rdx, [rsi+70h]; struct IStream *
0x18000b8ea  call    ?Open@CStream@@QEAAJPEAUIStream@@T_LARGE_INTEGER@@@Z; CStream::Open(IStream *,_LARGE_INTEGER)
0x18000b8ef  mov     edi, eax
0x18000b8f1  test    eax, eax
0x18000b8f3  js      short loc_18000B95E
0x18000b8f5  xor     edx, edx; Val
0x18000b8f7  lea     rcx, [rbp+370h+var_37C]; void *
0x18000b8fb  mov     r8d, 354h; Size
0x18000b901  call    memset_0
0x18000b906  mov     rcx, [rsp+470h+var_440]
0x18000b90b  lea     r8, [rbp+370h+var_380]
0x18000b90f  mov     [rbp+370h+var_380], 358h
0x18000b916  mov     rdx, rbx
0x18000b919  mov     rax, [rcx]
0x18000b91c  mov     rax, [rax+28h]
0x18000b920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b925  mov     edi, eax
0x18000b927  test    eax, eax
0x18000b929  js      short loc_18000B95E
0x18000b92b  lea     rcx, [rsp+470h+var_430]; this
0x18000b930  call    ??0CDescriptor@@QEAA@XZ; CDescriptor::CDescriptor(void)
0x18000b935  xor     r8d, r8d; struct IStream *
0x18000b938  lea     rdx, [rbp+370h+var_380]; struct _DMUS_OBJECTDESC *
0x18000b93c  lea     rcx, [rsp+470h+var_430]; this
0x18000b941  call    ?Set@CDescriptor@@QEAAXPEAU_DMUS_OBJECTDESC@@PEAUIStream@@@Z; CDescriptor::Set(_DMUS_OBJECTDESC *,IStream *)
0x18000b946  lea     rdx, [rsp+470h+var_430]; struct CDescriptor *
0x18000b94b  lea     rcx, [rsi+8]; this
0x18000b94f  call    ?Merge@CDescriptor@@QEAAXPEAV1@@Z; CDescriptor::Merge(CDescriptor *)
0x18000b954  lea     rcx, [rsp+470h+var_430]; this
0x18000b959  call    ??1CDescriptor@@QEAA@XZ; CDescriptor::~CDescriptor(void)
0x18000b95e  mov     rcx, rbx; this
0x18000b961  call    ?Release@CStream@@UEAAKXZ; CStream::Release(void)
0x18000b966  jmp     short loc_18000B96D
0x18000b968  mov     edi, 8007000Eh
0x18000b96d  mov     rcx, [rsp+470h+var_440]
0x18000b972  mov     rax, [rcx]
0x18000b975  mov     rax, [rax+10h]
0x18000b979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b97e  mov     eax, edi
0x18000b980  mov     rcx, [rbp+370h+var_20]
0x18000b987  xor     rcx, rsp; StackCookie
0x18000b98a  call    __security_check_cookie
0x18000b98f  lea     r11, [rsp+470h+var_10]
0x18000b997  mov     rbx, [r11+28h]
0x18000b99b  mov     rsi, [r11+30h]
0x18000b99f  mov     rsp, r11
0x18000b9a2  pop     r14
0x18000b9a4  pop     rdi
0x18000b9a5  pop     rbp
0x18000b9a6  retn
```
