# CWrapperOutputPin::GetUncompSurfacesInfo(_GUID const *,_tag_AMVAUncompBufferInfo *)

- ea: `0x180019c60`
- end: `0x180019d05`
- name: `?GetUncompSurfacesInfo@CWrapperOutputPin@@UEAAJPEBU_GUID@@PEAU_tag_AMVAUncompBufferInfo@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(CWrapperOutputPin *__hidden this, const struct _GUID *, struct _tag_AMVAUncompBufferInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180019c60`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWrapperOutputPin::GetUncompSurfacesInfo(
        CWrapperOutputPin *this,
        const struct _GUID *a2,
        struct _tag_AMVAUncompBufferInfo *a3)
{
  __int64 v3; // rax
  int v6; // ebx
  void (*v7)(void); // rax
  __int64 v9; // [rsp+20h] [rbp-28h] BYREF

  v3 = *((_QWORD *)this - 20);
  v9 = 0;
  v6 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v3 + 160))(
         *(_QWORD *)(v3 + 160),
         &IID_IAMVideoAcceleratorNotify,
         &v9);
  if ( v6 < 0 )
  {
    if ( v9 )
    {
      v7 = *(void (**)(void))(*(_QWORD *)v9 + 16LL);
      goto LABEL_6;
    }
  }
  else
  {
    v6 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, struct _tag_AMVAUncompBufferInfo *))(*(_QWORD *)v9 + 24LL))(
           v9,
           a2,
           a3);
    if ( v9 )
    {
      v7 = *(void (**)(void))(*(_QWORD *)v9 + 16LL);
LABEL_6:
      v7();
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180019c60  push    rbx
0x180019c62  push    rsi
0x180019c63  push    rdi
0x180019c64  sub     rsp, 30h
0x180019c68  mov     rax, cs:__security_cookie
0x180019c6f  xor     rax, rsp
0x180019c72  mov     [rsp+48h+var_20], rax
0x180019c77  mov     rax, [rcx-0A0h]
0x180019c7e  mov     rsi, r8
0x180019c81  mov     [rsp+48h+var_28], 0
0x180019c8a  lea     r8, [rsp+48h+var_28]
0x180019c8f  mov     rdi, rdx
0x180019c92  lea     rdx, IID_IAMVideoAcceleratorNotify
0x180019c99  mov     rcx, [rax+0A0h]
0x180019ca0  mov     rax, [rcx]
0x180019ca3  mov     rax, [rax]
0x180019ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cab  mov     rcx, [rsp+48h+var_28]
0x180019cb0  mov     ebx, eax
0x180019cb2  test    eax, eax
0x180019cb4  js      short loc_180019CDD
0x180019cb6  mov     rax, [rcx]
0x180019cb9  mov     r8, rsi
0x180019cbc  mov     rdx, rdi
0x180019cbf  mov     rax, [rax+18h]
0x180019cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cc8  mov     rcx, [rsp+48h+var_28]
0x180019ccd  mov     ebx, eax
0x180019ccf  test    rcx, rcx
0x180019cd2  jz      short loc_180019CEE
0x180019cd4  mov     rdx, [rcx]
0x180019cd7  mov     rax, [rdx+10h]
0x180019cdb  jmp     short loc_180019CE9
0x180019cdd  test    rcx, rcx
0x180019ce0  jz      short loc_180019CEE
0x180019ce2  mov     rax, [rcx]
0x180019ce5  mov     rax, [rax+10h]
0x180019ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cee  mov     eax, ebx
0x180019cf0  mov     rcx, [rsp+48h+var_20]
0x180019cf5  xor     rcx, rsp; StackCookie
0x180019cf8  call    __security_check_cookie
0x180019cfd  add     rsp, 30h
0x180019d01  pop     rdi
0x180019d02  pop     rsi
0x180019d03  pop     rbx
0x180019d04  retn
```
