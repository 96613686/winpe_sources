# Win32LiveSystemProvider::SuspendThread(void *,void * *)

- ea: `0x180015ec0`
- end: `0x180016013`
- name: `?SuspendThread@Win32LiveSystemProvider@@UEAAKPEAXPEAPEAX@Z`
- size: `339`
- prototype: `unsigned int(Win32LiveSystemProvider *__hidden this, void *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180015ec0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x180015edd`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x180015edd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015f6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015f6e`

## pseudocode

```c
DWORD __fastcall Win32LiveSystemProvider::SuspendThread(Win32LiveSystemProvider *this, void *a2, void **a3)
{
  void *v6; // rcx
  int (__fastcall *v8)(HANDLE *, __int64, _QWORD, void *, _DWORD); // rax
  int v9; // eax
  __int64 (__fastcall *v10)(void *, __int64, _QWORD *); // rax
  int v11; // eax
  __int64 (__fastcall *v12)(void *, __int64, _QWORD *); // rax
  _QWORD v13[2]; // [rsp+40h] [rbp-38h] BYREF
  _QWORD v14[2]; // [rsp+50h] [rbp-28h] BYREF
  void *v15; // [rsp+60h] [rbp-18h]
  HANDLE hObject; // [rsp+B0h] [rbp+38h] BYREF

  if ( !a3 )
    goto LABEL_2;
  if ( *a3 )
    return 1;
  v8 = (int (__fastcall *)(HANDLE *, __int64, _QWORD, void *, _DWORD))*((_QWORD *)this + 50);
  hObject = 0;
  if ( v8 && *((_QWORD *)this + 51) )
  {
    if ( v8(&hObject, 1, 0, a2, 0) < 0 )
      return -1;
    v9 = (*((__int64 (__fastcall **)(HANDLE, void *, _QWORD, _QWORD, _DWORD, _DWORD))this + 51))(
           hObject,
           a2,
           0,
           0,
           0,
           0);
  }
  else
  {
    v10 = (__int64 (__fastcall *)(void *, __int64, _QWORD *))*((_QWORD *)this + 52);
    v6 = a2;
    if ( !v10 )
      return SuspendThread(v6);
    v15 = 0;
    v14[0] = 0;
    v14[1] = 1;
    v11 = v10(a2, 51, v14);
    if ( v11 < 0 )
    {
      if ( v11 == -1073741821 )
      {
LABEL_2:
        v6 = a2;
        return SuspendThread(v6);
      }
      return -1;
    }
    hObject = v15;
    v13[0] = v15;
    v12 = (__int64 (__fastcall *)(void *, __int64, _QWORD *))*((_QWORD *)this + 52);
    v13[1] = 0;
    v9 = v12(a2, 52, v13);
  }
  if ( v9 >= 0 )
  {
    *a3 = hObject;
    return 0;
  }
  CloseHandle(hObject);
  return -1;
}

```

## disassembly

```asm
0x180015ec0  push    rbp
0x180015ec2  push    rbx
0x180015ec3  push    rsi
0x180015ec4  push    rdi
0x180015ec5  mov     rbp, rsp
0x180015ec8  sub     rsp, 78h
0x180015ecc  mov     rsi, r8
0x180015ecf  mov     rbx, rdx
0x180015ed2  mov     rdi, rcx
0x180015ed5  test    r8, r8
0x180015ed8  jnz     short loc_180015EE8
0x180015eda  mov     rcx, rbx; hThread
0x180015edd  call    cs:__imp_SuspendThread
0x180015ee3  jmp     loc_18001600A
0x180015ee8  cmp     qword ptr [r8], 0
0x180015eec  jz      short loc_180015EF8
0x180015eee  mov     eax, 1
0x180015ef3  jmp     loc_18001600A
0x180015ef8  mov     rax, [rcx+190h]
0x180015eff  mov     [rbp+hObject], 0
0x180015f07  test    rax, rax
0x180015f0a  jz      short loc_180015F79
0x180015f0c  cmp     qword ptr [rcx+198h], 0
0x180015f14  jz      short loc_180015F79
0x180015f16  xor     r8d, r8d
0x180015f19  mov     [rsp+78h+var_58], 0
0x180015f21  mov     r9, rbx
0x180015f24  lea     rcx, [rbp+hObject]
0x180015f28  lea     edx, [r8+1]
0x180015f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f31  test    eax, eax
0x180015f33  js      loc_180016007
0x180015f39  mov     rcx, [rbp+hObject]
0x180015f3d  xor     r9d, r9d
0x180015f40  mov     rax, [rdi+198h]
0x180015f47  xor     r8d, r8d
0x180015f4a  mov     [rsp+78h+var_50], 0
0x180015f52  mov     rdx, rbx
0x180015f55  mov     [rsp+78h+var_58], 0
0x180015f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f62  test    eax, eax
0x180015f64  jns     loc_180015FF1
0x180015f6a  mov     rcx, [rbp+hObject]; hObject
0x180015f6e  call    cs:__imp_CloseHandle
0x180015f74  jmp     loc_180016007
0x180015f79  mov     rax, [rcx+1A0h]
0x180015f80  mov     rcx, rbx
0x180015f83  test    rax, rax
0x180015f86  jz      loc_180015EDD
0x180015f8c  mov     r9d, 18h
0x180015f92  mov     [rbp+var_18], 0
0x180015f9a  lea     r8, [rbp+var_28]
0x180015f9e  mov     [rbp+var_28], 0
0x180015fa6  mov     [rbp+var_20], 1
0x180015fae  lea     edx, [r9+1Bh]
0x180015fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fb7  test    eax, eax
0x180015fb9  js      short loc_180015FFC
0x180015fbb  mov     rax, [rbp+var_18]
0x180015fbf  lea     r8, [rbp+var_38]
0x180015fc3  mov     r9d, 10h
0x180015fc9  mov     [rbp+hObject], rax
0x180015fcd  mov     [rbp+var_38], rax
0x180015fd1  mov     rcx, rbx
0x180015fd4  mov     rax, [rdi+1A0h]
0x180015fdb  mov     [rbp+var_30], 0
0x180015fe3  lea     edx, [r9+24h]
0x180015fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fec  jmp     loc_180015F62
0x180015ff1  mov     rax, [rbp+hObject]
0x180015ff5  mov     [rsi], rax
0x180015ff8  xor     eax, eax
0x180015ffa  jmp     short loc_18001600A
0x180015ffc  cmp     eax, 0C0000003h
0x180016001  jz      loc_180015EDA
0x180016007  or      eax, 0FFFFFFFFh
0x18001600a  add     rsp, 78h
0x18001600e  pop     rdi
0x18001600f  pop     rsi
0x180016010  pop     rbx
0x180016011  pop     rbp
0x180016012  retn
```
