# CWrappedDocFile::StatEntry(CDfName const *,SIterBuffer *,tagSTATSTG *)

- ea: `0x18003fa80`
- end: `0x18003fc2a`
- name: `?StatEntry@CWrappedDocFile@@QEAAJPEBVCDfName@@PEAUSIterBuffer@@PEAUtagSTATSTG@@@Z`
- size: `426`
- prototype: `__int64 __fastcall(CWrappedDocFile *__hidden this, const struct CDfName *, struct SIterBuffer *, struct tagSTATSTG *)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180022338`
- `0x18003fa80`

## callees

- `0x18001a990`
- `0x1800222fc`
- `0x180022d8c`
- `0x18003fa80`
- `0x18003fc30`
- `0x180060a48`
- `0x180060d04`
- `0x18006141c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003fbe2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003fbe2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fbd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fbd8`

## pseudocode

```c
__int64 __fastcall CWrappedDocFile::StatEntry(
        CWrappedDocFile *this,
        const struct CDfName *a2,
        struct SIterBuffer *a3,
        struct tagSTATSTG *a4)
{
  struct CDfName *v8; // rbp
  int IsEntry; // eax
  struct CDfName *v10; // rbx
  unsigned int v11; // ebx
  struct CUpdate *Base; // rax
  __int64 v13; // rdx
  PTSetMember *v14; // rcx
  __int64 v15; // rdx
  CDocFile *v16; // rcx
  int v17; // eax
  void *v18; // rax
  struct CDfName *v20; // [rsp+40h] [rbp+8h] BYREF
  struct CDfName *v21; // [rsp+48h] [rbp+10h] BYREF

  v20 = 0;
  v21 = a2;
  v8 = a2;
  IsEntry = CUpdateList::IsEntry((char *)this + 128, a2, &v20);
  if ( IsEntry == 1 )
    return (unsigned int)-2147287038;
  if ( !IsEntry )
  {
    if ( a3 )
    {
      v10 = v20;
      CDfName::Set(a3, v20);
      *((_DWORD *)a3 + 17) = *((_DWORD *)v10 + 34) & 3;
      return 0;
    }
    Base = CUpdateList::FindBase(v20, &v21);
    if ( Base )
    {
      v13 = *((_QWORD *)Base + 18);
      if ( v13 )
        v14 = (PTSetMember *)(v13 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
      else
        v14 = 0;
      return (unsigned int)PTSetMember::Stat(v14, a4, 0);
    }
    v8 = v21;
  }
  v15 = *((_QWORD *)this + 15);
  if ( !v15 || !(v15 + *(_QWORD *)NtCurrentTeb()->ReservedForOle) )
    return (unsigned int)-2147287038;
  v16 = (CDocFile *)(v15 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
  if ( *(_DWORD *)v16 == 1279673411 )
  {
    v17 = CDocFile::StatEntry(v16, v8, a3, a4);
  }
  else
  {
    if ( *(_DWORD *)v16 != 1279673431 )
      return (unsigned int)-2147287039;
    v17 = CWrappedDocFile::StatEntry(v16, v8, a3, a4);
  }
  v11 = v17;
  if ( v17 >= 0 && !(unsigned int)CDfName::IsEqual(a2, v8) )
  {
    if ( a3 )
    {
      CDfName::Set(a3, a2);
    }
    else
    {
      CoTaskMemFree(*(LPVOID *)a4);
      v18 = CoTaskMemAlloc(*((unsigned __int16 *)a2 + 32));
      *(_QWORD *)a4 = v18;
      if ( v18 )
        memcpy_0(v18, a2, *((unsigned __int16 *)a2 + 32));
      else
        return (unsigned int)-2147287032;
    }
  }
  return v11;
}

```

## disassembly

```asm
0x18003fa80  mov     rax, rsp
0x18003fa83  mov     [rax+18h], rbx
0x18003fa87  mov     [rax+20h], rbp
0x18003fa8b  push    rsi
0x18003fa8c  push    rdi
0x18003fa8d  push    r14
0x18003fa8f  sub     rsp, 20h
0x18003fa93  mov     rdi, r8
0x18003fa96  mov     qword ptr [rax+8], 0
0x18003fa9e  mov     rbx, rcx
0x18003faa1  mov     [rax+10h], rdx
0x18003faa5  sub     rcx, 0FFFFFFFFFFFFFF80h
0x18003faa9  lea     r8, [rax+8]
0x18003faad  mov     r14, r9
0x18003fab0  mov     rsi, rdx
0x18003fab3  mov     rbp, rdx
0x18003fab6  call    ?IsEntry@CUpdateList@@QEAA?AW4UlIsEntry@@PEBVCDfName@@PEAPEAVCUpdate@@@Z; CUpdateList::IsEntry(CDfName const *,CUpdate * *)
0x18003fabb  cmp     eax, 1
0x18003fabe  jz      loc_18003FC10
0x18003fac4  test    eax, eax
0x18003fac6  jnz     short loc_18003FB41
0x18003fac8  test    rdi, rdi
0x18003facb  jz      short loc_18003FAF0
0x18003facd  mov     rbx, [rsp+38h+arg_0]
0x18003fad2  mov     rcx, rdi; this
0x18003fad5  mov     rdx, rbx; struct CDfName *
0x18003fad8  call    ?Set@CDfName@@QEAAXPEBV1@@Z; CDfName::Set(CDfName const *)
0x18003fadd  mov     eax, [rbx+88h]
0x18003fae3  and     eax, 3
0x18003fae6  mov     [rdi+44h], eax
0x18003fae9  xor     ebx, ebx
0x18003faeb  jmp     loc_18003FC15
0x18003faf0  mov     rcx, [rsp+38h+arg_0]; this
0x18003faf5  lea     rdx, [rsp+38h+arg_8]; struct CDfName **
0x18003fafa  call    ?FindBase@CUpdateList@@SAPEAVCUpdate@@PEAV2@PEAPEBVCDfName@@@Z; CUpdateList::FindBase(CUpdate *,CDfName const * *)
0x18003faff  test    rax, rax
0x18003fb02  jz      short loc_18003FB3C
0x18003fb04  mov     rdx, [rax+90h]
0x18003fb0b  test    rdx, rdx
0x18003fb0e  jz      short loc_18003FB28
0x18003fb10  mov     rax, gs:30h
0x18003fb19  mov     rcx, [rax+1758h]
0x18003fb20  mov     rcx, [rcx]
0x18003fb23  add     rcx, rdx
0x18003fb26  jmp     short loc_18003FB2A
0x18003fb28  xor     ecx, ecx; this
0x18003fb2a  xor     r8d, r8d; unsigned int
0x18003fb2d  mov     rdx, r14; struct tagSTATSTG *
0x18003fb30  call    ?Stat@PTSetMember@@QEAAJPEAUtagSTATSTG@@K@Z; PTSetMember::Stat(tagSTATSTG *,ulong)
0x18003fb35  mov     ebx, eax
0x18003fb37  jmp     loc_18003FC15
0x18003fb3c  mov     rbp, [rsp+38h+arg_8]
0x18003fb41  mov     rdx, [rbx+78h]
0x18003fb45  test    rdx, rdx
0x18003fb48  jz      loc_18003FC10
0x18003fb4e  mov     rax, gs:30h
0x18003fb57  mov     rcx, [rax+1758h]
0x18003fb5e  mov     rax, [rcx]
0x18003fb61  add     rax, rdx
0x18003fb64  jz      loc_18003FC10
0x18003fb6a  mov     rax, gs:30h
0x18003fb73  mov     rcx, [rax+1758h]
0x18003fb7a  mov     rcx, [rcx]
0x18003fb7d  add     rcx, rdx; this
0x18003fb80  cmp     dword ptr [rcx], 4C464443h
0x18003fb86  jnz     short loc_18003FB98
0x18003fb88  mov     r9, r14; struct tagSTATSTG *
0x18003fb8b  mov     r8, rdi; struct SIterBuffer *
0x18003fb8e  mov     rdx, rbp; struct CDfName *
0x18003fb91  call    ?StatEntry@CDocFile@@QEAAJPEBVCDfName@@PEAUSIterBuffer@@PEAUtagSTATSTG@@@Z; CDocFile::StatEntry(CDfName const *,SIterBuffer *,tagSTATSTG *)
0x18003fb96  jmp     short loc_18003FBAE
0x18003fb98  cmp     dword ptr [rcx], 4C464457h
0x18003fb9e  jnz     short loc_18003FC09
0x18003fba0  mov     r9, r14; struct tagSTATSTG *
0x18003fba3  mov     r8, rdi; struct SIterBuffer *
0x18003fba6  mov     rdx, rbp; struct CDfName *
0x18003fba9  call    ?StatEntry@CWrappedDocFile@@QEAAJPEBVCDfName@@PEAUSIterBuffer@@PEAUtagSTATSTG@@@Z; CWrappedDocFile::StatEntry(CDfName const *,SIterBuffer *,tagSTATSTG *)
0x18003fbae  mov     ebx, eax
0x18003fbb0  test    eax, eax
0x18003fbb2  js      short loc_18003FC15
0x18003fbb4  mov     rdx, rbp; struct CDfName *
0x18003fbb7  mov     rcx, rsi; this
0x18003fbba  call    ?IsEqual@CDfName@@QEBAHPEBV1@@Z; CDfName::IsEqual(CDfName const *)
0x18003fbbf  test    eax, eax
0x18003fbc1  jnz     short loc_18003FC15
0x18003fbc3  test    rdi, rdi
0x18003fbc6  jz      short loc_18003FBD5
0x18003fbc8  mov     rdx, rsi; struct CDfName *
0x18003fbcb  mov     rcx, rdi; this
0x18003fbce  call    ?Set@CDfName@@QEAAXPEBV1@@Z; CDfName::Set(CDfName const *)
0x18003fbd3  jmp     short loc_18003FC15
0x18003fbd5  mov     rcx, [r14]; pv
0x18003fbd8  call    cs:__imp_CoTaskMemFree
0x18003fbde  movzx   ecx, word ptr [rsi+40h]; cb
0x18003fbe2  call    cs:__imp_CoTaskMemAlloc
0x18003fbe8  mov     [r14], rax
0x18003fbeb  test    rax, rax
0x18003fbee  jnz     short loc_18003FBF7
0x18003fbf0  mov     ebx, 80030008h
0x18003fbf5  jmp     short loc_18003FC15
0x18003fbf7  movzx   r8d, word ptr [rsi+40h]; Size
0x18003fbfc  mov     rdx, rsi; Src
0x18003fbff  mov     rcx, rax; void *
0x18003fc02  call    memcpy_0
0x18003fc07  jmp     short loc_18003FC15
0x18003fc09  mov     ebx, 80030001h
0x18003fc0e  jmp     short loc_18003FC15
0x18003fc10  mov     ebx, 80030002h
0x18003fc15  mov     rbp, [rsp+38h+arg_18]
0x18003fc1a  mov     eax, ebx
0x18003fc1c  mov     rbx, [rsp+38h+arg_10]
0x18003fc21  add     rsp, 20h
0x18003fc25  pop     r14
0x18003fc27  pop     rdi
0x18003fc28  pop     rsi
0x18003fc29  retn
```
