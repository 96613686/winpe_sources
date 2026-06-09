# CPidlMgr::CreatePIDLFromPropertyStore(IPropertyStore *)

- ea: `0x180002b50`
- end: `0x180002c5f`
- name: `?CreatePIDLFromPropertyStore@CPidlMgr@@QEAAPEAU_ITEMID_CHILD@@PEAUIPropertyStore@@@Z`
- size: `271`
- prototype: `struct _ITEMID_CHILD *__fastcall(CPidlMgr *__hidden this, struct IPropertyStore *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004100`

## callees

- `0x180002b50`
- `0x180006dcc`
- `0x180038b28`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002c36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002c36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002c07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002c07`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct _ITEMID_CHILD *__fastcall CPidlMgr::CreatePIDLFromPropertyStore(CPidlMgr *this, struct IPropertyStore *a2)
{
  int v3; // eax
  __int64 v4; // rbp
  __int16 v5; // di
  unsigned int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // rsi
  void *v10; // rax
  size_t Size; // [rsp+58h] [rbp+10h] BYREF
  void *Src; // [rsp+60h] [rbp+18h] BYREF
  __int64 v13; // [rsp+68h] [rbp+20h] BYREF

  v13 = 0;
  v3 = ((__int64 (__fastcall *)(struct IPropertyStore *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_e318ad57_0aa0_450f_aca5_6fab7103d917,
         &v13);
  v4 = 0;
  LODWORD(Size) = 0;
  Src = 0;
  if ( v3 >= 0 && (*(int (__fastcall **)(__int64, void **, size_t *))(*(_QWORD *)v13 + 40LL))(v13, &Src, &Size) >= 0 )
  {
    v5 = Size + 6;
    v6 = Size + 14;
    if ( (unsigned int)(Size + 14) <= 0xFFFF )
    {
      v7 = *((_QWORD *)this + 4);
      if ( v7 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 24LL))(v7, v6);
      }
      else
      {
        v10 = CoTaskMemAlloc(v6);
        v8 = (__int64)v10;
        if ( v10 )
        {
          memset_0(v10, 0, v6);
          *(_WORD *)v8 = v6 - 2;
          *(_WORD *)(v8 + 4) = v5;
          goto LABEL_7;
        }
      }
      if ( v8 )
      {
LABEL_7:
        memcpy_0((void *)(v8 + 10), Src, (unsigned int)Size);
        *(_DWORD *)(v8 + 6) = 170466544;
        v4 = v8;
      }
    }
    CoTaskMemFree(Src);
  }
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return (struct _ITEMID_CHILD *)v4;
}

```

## disassembly

```asm
0x180002b50  push    rbx
0x180002b52  push    rbp
0x180002b53  push    rsi
0x180002b54  push    rdi
0x180002b55  push    r14
0x180002b57  sub     rsp, 20h
0x180002b5b  mov     r9, rdx
0x180002b5e  mov     rsi, rcx
0x180002b61  xor     ebx, ebx
0x180002b63  mov     [rsp+48h+arg_18], rbx
0x180002b68  mov     rax, [rdx]
0x180002b6b  lea     r8, [rsp+48h+arg_18]
0x180002b70  lea     rdx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917
0x180002b77  mov     rcx, r9
0x180002b7a  mov     rax, [rax]
0x180002b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b82  mov     ebp, ebx
0x180002b84  mov     dword ptr [rsp+48h+Size], ebx
0x180002b88  mov     [rsp+48h+Src], rbx
0x180002b8d  test    eax, eax
0x180002b8f  js      short loc_180002C0E
0x180002b91  mov     rcx, [rsp+48h+arg_18]
0x180002b96  mov     rax, [rcx]
0x180002b99  lea     r8, [rsp+48h+Size]
0x180002b9e  lea     rdx, [rsp+48h+Src]
0x180002ba3  mov     rax, [rax+28h]
0x180002ba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bac  test    eax, eax
0x180002bae  js      short loc_180002C0E
0x180002bb0  mov     edi, dword ptr [rsp+48h+Size]
0x180002bb4  add     edi, 6
0x180002bb7  lea     ebx, [rdi+8]
0x180002bba  cmp     ebx, 0FFFFh
0x180002bc0  ja      short loc_180002C02
0x180002bc2  mov     rcx, [rsi+20h]
0x180002bc6  mov     r14d, ebx
0x180002bc9  test    rcx, rcx
0x180002bcc  jz      short loc_180002C33
0x180002bce  mov     rax, [rcx]
0x180002bd1  mov     edx, r14d
0x180002bd4  mov     rax, [rax+18h]
0x180002bd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bdd  mov     rsi, rax
0x180002be0  test    rsi, rsi
0x180002be3  jz      short loc_180002C02
0x180002be5  mov     r8d, dword ptr [rsp+48h+Size]; Size
0x180002bea  lea     rcx, [rsi+0Ah]; void *
0x180002bee  mov     rdx, [rsp+48h+Src]; Src
0x180002bf3  call    memcpy_0
0x180002bf8  mov     dword ptr [rsi+6], 0A291CF0h
0x180002bff  mov     rbp, rsi
0x180002c02  mov     rcx, [rsp+48h+Src]; pv
0x180002c07  call    cs:__imp_CoTaskMemFree
0x180002c0d  nop
0x180002c0e  mov     rcx, [rsp+48h+arg_18]
0x180002c13  test    rcx, rcx
0x180002c16  jz      short loc_180002C25
0x180002c18  mov     rdx, [rcx]
0x180002c1b  mov     rax, [rdx+10h]
0x180002c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c24  nop
0x180002c25  mov     rax, rbp
0x180002c28  add     rsp, 20h
0x180002c2c  pop     r14
0x180002c2e  pop     rdi
0x180002c2f  pop     rsi
0x180002c30  pop     rbp
0x180002c31  pop     rbx
0x180002c32  retn
0x180002c33  mov     rcx, r14; cb
0x180002c36  call    cs:__imp_CoTaskMemAlloc
0x180002c3c  mov     rsi, rax
0x180002c3f  test    rax, rax
0x180002c42  jz      short loc_180002BE0
0x180002c44  mov     r8, r14; Size
0x180002c47  xor     edx, edx; Val
0x180002c49  mov     rcx, rax; void *
0x180002c4c  call    memset_0
0x180002c51  sub     bx, 2
0x180002c55  mov     [rsi], bx
0x180002c58  mov     [rsi+4], di
0x180002c5c  jmp     short loc_180002BE5
```
