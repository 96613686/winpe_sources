# CreateRemoteProxy6432(HWND__ *,long,_GUID const &,void * *)

- ea: `0x18001bb6c`
- end: `0x18001bc31`
- name: `?CreateRemoteProxy6432@@YAJPEAUHWND__@@JAEBU_GUID@@PEAPEAX@Z`
- size: `197`
- prototype: `HRESULT __fastcall(HWND, unsigned int, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800097e0`
- `0x18000bc30`

## callees

- `0x18001bb6c`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001bba7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001bba7`

## pseudocode

```c
HRESULT __fastcall CreateRemoteProxy6432(HWND a1, unsigned int a2, const struct _GUID *a3, void **a4)
{
  unsigned int v7; // ebp
  HRESULT result; // eax
  int v9; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v11[6]; // [rsp+38h] [rbp-30h] BYREF

  ppv = 0;
  v7 = (unsigned int)a1;
  result = CoCreateInstance(&CLSID_RemoteProxyFactory32, 0, 4u, &IID_IRemoteProxyFactory, &ppv);
  if ( result >= 0 )
  {
    if ( !ppv )
      return -2147024882;
    v11[0] = 0;
    v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD *))(*(_QWORD *)ppv + 56LL))(ppv, v7, a2, v11);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( v9 >= 0 )
    {
      if ( !v11[0] )
        return -2147024882;
      v9 = (**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))v11[0])(v11[0], a3, a4);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v11[0] + 16LL))(v11[0]);
    }
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x18001bb6c  push    rbx
0x18001bb6e  push    rbp
0x18001bb6f  push    rsi
0x18001bb70  push    rdi
0x18001bb71  sub     rsp, 48h
0x18001bb75  mov     ebx, edx
0x18001bb77  mov     [rsp+68h+var_38], 0
0x18001bb80  xor     edx, edx; pUnkOuter
0x18001bb82  lea     rax, [rsp+68h+var_38]
0x18001bb87  mov     rdi, r9
0x18001bb8a  mov     [rsp+68h+ppv], rax; ppv
0x18001bb8f  mov     rsi, r8
0x18001bb92  lea     r9, IID_IRemoteProxyFactory; riid
0x18001bb99  mov     rbp, rcx
0x18001bb9c  lea     rcx, CLSID_RemoteProxyFactory32; rclsid
0x18001bba3  lea     r8d, [rdx+4]; dwClsContext
0x18001bba7  call    cs:__imp_CoCreateInstance
0x18001bbad  test    eax, eax
0x18001bbaf  js      short loc_18001BC28
0x18001bbb1  mov     rcx, [rsp+68h+var_38]
0x18001bbb6  test    rcx, rcx
0x18001bbb9  jnz     short loc_18001BBC2
0x18001bbbb  mov     eax, 8007000Eh
0x18001bbc0  jmp     short loc_18001BC28
0x18001bbc2  mov     [rsp+68h+var_30], 0
0x18001bbcb  lea     r9, [rsp+68h+var_30]
0x18001bbd0  mov     rax, [rcx]
0x18001bbd3  mov     edx, ebp
0x18001bbd5  mov     r8d, ebx
0x18001bbd8  mov     rax, [rax+38h]
0x18001bbdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbe1  mov     rcx, [rsp+68h+var_38]
0x18001bbe6  mov     ebx, eax
0x18001bbe8  mov     rdx, [rcx]
0x18001bbeb  mov     rax, [rdx+10h]
0x18001bbef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbf4  test    ebx, ebx
0x18001bbf6  js      short loc_18001BC26
0x18001bbf8  mov     rcx, [rsp+68h+var_30]
0x18001bbfd  test    rcx, rcx
0x18001bc00  jz      short loc_18001BBBB
0x18001bc02  mov     rax, [rcx]
0x18001bc05  mov     r8, rdi
0x18001bc08  mov     rdx, rsi
0x18001bc0b  mov     rax, [rax]
0x18001bc0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc13  mov     rcx, [rsp+68h+var_30]
0x18001bc18  mov     ebx, eax
0x18001bc1a  mov     rdx, [rcx]
0x18001bc1d  mov     rax, [rdx+10h]
0x18001bc21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc26  mov     eax, ebx
0x18001bc28  add     rsp, 48h
0x18001bc2c  pop     rdi
0x18001bc2d  pop     rsi
0x18001bc2e  pop     rbp
0x18001bc2f  pop     rbx
0x18001bc30  retn
```
