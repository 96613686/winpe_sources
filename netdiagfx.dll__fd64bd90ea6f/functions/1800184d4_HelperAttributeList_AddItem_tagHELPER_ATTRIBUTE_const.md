# HelperAttributeList::AddItem(tagHELPER_ATTRIBUTE const &)

- ea: `0x1800184d4`
- end: `0x1800185a7`
- name: `?AddItem@HelperAttributeList@@AEAAJAEBUtagHELPER_ATTRIBUTE@@@Z`
- size: `211`
- prototype: `__int64 __fastcall(HelperAttributeList *__hidden this, const struct tagHELPER_ATTRIBUTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018ae4`

## callees

- `0x180009f54`
- `0x18000bda4`
- `0x1800184d4`
- `0x18001a83c`
- `0x18002c802`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800184eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018555`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800184eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018555`

## pseudocode

```c
__int64 __fastcall HelperAttributeList::AddItem(HelperAttributeList *this, const struct tagHELPER_ATTRIBUTE *a2)
{
  struct tagHELPER_ATTRIBUTE *v4; // rax
  struct tagHELPER_ATTRIBUTE *v5; // rsi
  int Item; // ebx
  const unsigned __int16 *pwszName; // rdx
  struct tagHELPER_ATTRIBUTE *v9; // rcx
  _OWORD *v10; // rax
  __int64 v11; // rcx
  struct HelperAttributeList::HelperAttributeListItem *v12; // [rsp+60h] [rbp+18h] BYREF

  v4 = (struct tagHELPER_ATTRIBUTE *)CoTaskMemAlloc(0x90u);
  v5 = v4;
  if ( !v4 )
    return 2147942414LL;
  memset_0(v4, 0, sizeof(struct tagHELPER_ATTRIBUTE));
  Item = CopyHelperAttribute(v5, a2);
  if ( Item < 0 )
  {
LABEL_12:
    v9 = v5;
    goto LABEL_13;
  }
  pwszName = a2->pwszName;
  v12 = 0;
  Item = HelperAttributeList::GetItem(this, pwszName, &v12, 0);
  if ( Item < 0 )
  {
    v10 = CoTaskMemAlloc(0x10u);
    if ( v10 )
    {
      Item = 0;
      *v10 = 0;
      *(_QWORD *)v10 = v5;
      v11 = *((_QWORD *)this + 1);
      if ( v11 )
        *(_QWORD *)(v11 + 8) = v10;
      else
        *(_QWORD *)this = v10;
      ++*((_DWORD *)this + 4);
      *((_QWORD *)this + 1) = v10;
      return (unsigned int)Item;
    }
    Item = -2147024882;
    goto LABEL_12;
  }
  v9 = *(struct tagHELPER_ATTRIBUTE **)v12;
  *(_QWORD *)v12 = v5;
LABEL_13:
  FreeHelperAttributes(v9, 1u, 1);
  return (unsigned int)Item;
}

```

## disassembly

```asm
0x1800184d4  push    rbx
0x1800184d6  push    rsi
0x1800184d7  push    rdi
0x1800184d8  push    r14
0x1800184da  sub     rsp, 28h
0x1800184de  mov     rdi, rcx
0x1800184e1  mov     ebx, 90h
0x1800184e6  mov     ecx, ebx; cb
0x1800184e8  mov     r14, rdx
0x1800184eb  call    cs:__imp_CoTaskMemAlloc
0x1800184f1  mov     rsi, rax
0x1800184f4  test    rax, rax
0x1800184f7  jnz     short loc_180018503
0x1800184f9  mov     eax, 8007000Eh
0x1800184fe  jmp     loc_18001859D
0x180018503  mov     r8, rbx; Size
0x180018506  xor     edx, edx; Val
0x180018508  mov     rcx, rsi; void *
0x18001850b  call    memset_0
0x180018510  mov     rdx, r14; struct tagHELPER_ATTRIBUTE *
0x180018513  mov     rcx, rsi; struct tagHELPER_ATTRIBUTE *
0x180018516  call    ?CopyHelperAttribute@@YAJPEAUtagHELPER_ATTRIBUTE@@PEBU1@@Z; CopyHelperAttribute(tagHELPER_ATTRIBUTE *,tagHELPER_ATTRIBUTE const *)
0x18001851b  mov     ebx, eax
0x18001851d  test    eax, eax
0x18001851f  js      short loc_18001858B
0x180018521  mov     rdx, [r14]; unsigned __int16 *
0x180018524  lea     r8, [rsp+48h+arg_10]; struct HelperAttributeList::HelperAttributeListItem **
0x180018529  xor     r9d, r9d; struct HelperAttributeList::HelperAttributeListItem **
0x18001852c  mov     [rsp+48h+arg_10], 0
0x180018535  mov     rcx, rdi; this
0x180018538  call    ?GetItem@HelperAttributeList@@AEAAJPEBGPEAPEAUHelperAttributeListItem@1@1@Z; HelperAttributeList::GetItem(ushort const *,HelperAttributeList::HelperAttributeListItem * *,HelperAttributeList::HelperAttributeListItem * *)
0x18001853d  mov     ebx, eax
0x18001853f  test    eax, eax
0x180018541  js      short loc_180018550
0x180018543  mov     rax, [rsp+48h+arg_10]
0x180018548  mov     rcx, [rax]
0x18001854b  mov     [rax], rsi
0x18001854e  jmp     short loc_18001858E
0x180018550  mov     ecx, 10h; cb
0x180018555  call    cs:__imp_CoTaskMemAlloc
0x18001855b  test    rax, rax
0x18001855e  jz      short loc_180018586
0x180018560  xorps   xmm0, xmm0
0x180018563  xor     ebx, ebx
0x180018565  movups  xmmword ptr [rax], xmm0
0x180018568  mov     [rax], rsi
0x18001856b  mov     rcx, [rdi+8]
0x18001856f  test    rcx, rcx
0x180018572  jz      short loc_18001857A
0x180018574  mov     [rcx+8], rax
0x180018578  jmp     short loc_18001857D
0x18001857a  mov     [rdi], rax
0x18001857d  inc     dword ptr [rdi+10h]
0x180018580  mov     [rdi+8], rax
0x180018584  jmp     short loc_18001859B
0x180018586  mov     ebx, 8007000Eh
0x18001858b  mov     rcx, rsi; pv
0x18001858e  mov     edx, 1; unsigned int
0x180018593  mov     r8d, edx; int
0x180018596  call    ?FreeHelperAttributes@@YAXPEAUtagHELPER_ATTRIBUTE@@KH@Z; FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)
0x18001859b  mov     eax, ebx
0x18001859d  add     rsp, 28h
0x1800185a1  pop     r14
0x1800185a3  pop     rdi
0x1800185a4  pop     rsi
0x1800185a5  pop     rbx
0x1800185a6  retn
```
