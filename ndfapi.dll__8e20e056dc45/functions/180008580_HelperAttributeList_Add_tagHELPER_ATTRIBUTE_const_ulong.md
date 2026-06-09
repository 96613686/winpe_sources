# HelperAttributeList::Add(tagHELPER_ATTRIBUTE const *,ulong)

- ea: `0x180008580`
- end: `0x1800086a2`
- name: `?Add@HelperAttributeList@@QEAAJPEBUtagHELPER_ATTRIBUTE@@K@Z`
- size: `290`
- prototype: `__int64 __fastcall(struct tagHELPER_ATTRIBUTE ***this, const struct tagHELPER_ATTRIBUTE *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000a9e0`

## callees

- `0x180008580`
- `0x1800087f8`
- `0x180008a60`
- `0x18001f652`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800085b2`
- `ole32!CoTaskMemAlloc` at `0x180008638`
- `ole32!CoTaskMemAlloc` at `0x1800085b2`
- `ole32!CoTaskMemAlloc` at `0x180008638`

## pseudocode

```c
__int64 __fastcall HelperAttributeList::Add(
        struct tagHELPER_ATTRIBUTE ***this,
        const struct tagHELPER_ATTRIBUTE *a2,
        unsigned int a3)
{
  int v3; // ebx
  __int64 i; // rbp
  struct tagHELPER_ATTRIBUTE *v8; // rax
  struct tagHELPER_ATTRIBUTE *v9; // rsi
  struct tagHELPER_ATTRIBUTE **j; // rdx
  LPWSTR pwszName; // rcx
  char *v12; // r9
  int v13; // eax
  int v14; // r8d
  struct tagHELPER_ATTRIBUTE **v15; // rax
  struct tagHELPER_ATTRIBUTE **v16; // rcx
  struct tagHELPER_ATTRIBUTE *v17; // rcx

  v3 = 0;
  for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
  {
    if ( v3 < 0 )
      return (unsigned int)v3;
    v8 = (struct tagHELPER_ATTRIBUTE *)CoTaskMemAlloc(0x90u);
    v9 = v8;
    if ( v8 )
    {
      memset_0(v8, 0, sizeof(struct tagHELPER_ATTRIBUTE));
      v3 = CopyHelperAttribute(v9, &a2[i]);
      if ( v3 < 0 )
        goto LABEL_20;
      for ( j = *this; j; j = (struct tagHELPER_ATTRIBUTE **)j[1] )
      {
        pwszName = (*j)->pwszName;
        v12 = (char *)((char *)a2[i].pwszName - (char *)pwszName);
        do
        {
          v13 = *(unsigned __int16 *)&v12[(_QWORD)pwszName];
          v14 = *pwszName - v13;
          if ( v14 )
            break;
          ++pwszName;
        }
        while ( v13 );
        if ( !v14 )
        {
          v17 = *j;
          v3 = 0;
          *j = v9;
          goto LABEL_21;
        }
      }
      v15 = (struct tagHELPER_ATTRIBUTE **)CoTaskMemAlloc(0x10u);
      if ( !v15 )
      {
        v3 = -2147024882;
LABEL_20:
        v17 = v9;
LABEL_21:
        FreeHelperAttributes(v17, 1u, 1);
        continue;
      }
      v3 = 0;
      v15[1] = 0;
      *v15 = v9;
      v16 = this[1];
      if ( v16 )
        v16[1] = (struct tagHELPER_ATTRIBUTE *)v15;
      else
        *this = v15;
      this[1] = v15;
      ++*((_DWORD *)this + 4);
    }
    else
    {
      v3 = -2147024882;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180008580  push    rbx
0x180008582  push    rbp
0x180008583  push    rsi
0x180008584  push    rdi
0x180008585  push    r12
0x180008587  push    r14
0x180008589  push    r15
0x18000858b  sub     rsp, 20h
0x18000858f  xor     ebx, ebx
0x180008591  xor     ebp, ebp
0x180008593  mov     r15d, r8d
0x180008596  mov     r12, rdx
0x180008599  mov     rdi, rcx
0x18000859c  test    r8d, r8d
0x18000859f  jz      loc_180008691
0x1800085a5  test    ebx, ebx
0x1800085a7  js      loc_180008691
0x1800085ad  mov     ecx, 90h; cb
0x1800085b2  call    cs:__imp_CoTaskMemAlloc
0x1800085b8  mov     rsi, rax
0x1800085bb  test    rax, rax
0x1800085be  jnz     short loc_1800085CA
0x1800085c0  mov     ebx, 8007000Eh
0x1800085c5  jmp     loc_180008686
0x1800085ca  lea     r14, ds:0[rbp*8]
0x1800085d2  xor     edx, edx; Val
0x1800085d4  add     r14, rbp
0x1800085d7  mov     r8d, 90h; Size
0x1800085dd  shl     r14, 4
0x1800085e1  mov     rcx, rsi; void *
0x1800085e4  add     r14, r12
0x1800085e7  call    memset_0
0x1800085ec  mov     rdx, r14; struct tagHELPER_ATTRIBUTE *
0x1800085ef  mov     rcx, rsi; struct tagHELPER_ATTRIBUTE *
0x1800085f2  call    ?CopyHelperAttribute@@YAJPEAUtagHELPER_ATTRIBUTE@@PEBU1@@Z; CopyHelperAttribute(tagHELPER_ATTRIBUTE *,tagHELPER_ATTRIBUTE const *)
0x1800085f7  mov     ebx, eax
0x1800085f9  test    eax, eax
0x1800085fb  js      short loc_180008676
0x1800085fd  mov     r10, [r14]
0x180008600  mov     rdx, [rdi]
0x180008603  jmp     short loc_180008630
0x180008605  mov     rax, [rdx]
0x180008608  mov     r9, r10
0x18000860b  mov     rcx, [rax]
0x18000860e  sub     r9, rcx
0x180008611  movzx   r8d, word ptr [rcx]
0x180008615  movzx   eax, word ptr [rcx+r9]
0x18000861a  sub     r8d, eax
0x18000861d  jnz     short loc_180008627
0x18000861f  add     rcx, 2
0x180008623  test    eax, eax
0x180008625  jnz     short loc_180008611
0x180008627  test    r8d, r8d
0x18000862a  jz      short loc_18000865B
0x18000862c  mov     rdx, [rdx+8]
0x180008630  test    rdx, rdx
0x180008633  jnz     short loc_180008605
0x180008635  lea     ecx, [rdx+10h]; cb
0x180008638  call    cs:__imp_CoTaskMemAlloc
0x18000863e  test    rax, rax
0x180008641  jz      short loc_180008671
0x180008643  xor     ebx, ebx
0x180008645  mov     [rax+8], rbx
0x180008649  mov     [rax], rsi
0x18000864c  mov     rcx, [rdi+8]
0x180008650  test    rcx, rcx
0x180008653  jz      short loc_180008665
0x180008655  mov     [rcx+8], rax
0x180008659  jmp     short loc_180008668
0x18000865b  mov     rcx, [rdx]
0x18000865e  xor     ebx, ebx
0x180008660  mov     [rdx], rsi
0x180008663  jmp     short loc_180008679
0x180008665  mov     [rdi], rax
0x180008668  mov     [rdi+8], rax
0x18000866c  inc     dword ptr [rdi+10h]
0x18000866f  jmp     short loc_180008686
0x180008671  mov     ebx, 8007000Eh
0x180008676  mov     rcx, rsi; pv
0x180008679  mov     edx, 1; unsigned int
0x18000867e  mov     r8d, edx; int
0x180008681  call    ?FreeHelperAttributes@@YAXPEAUtagHELPER_ATTRIBUTE@@KH@Z; FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)
0x180008686  inc     ebp
0x180008688  cmp     ebp, r15d
0x18000868b  jb      loc_1800085A5
0x180008691  mov     eax, ebx
0x180008693  add     rsp, 20h
0x180008697  pop     r15
0x180008699  pop     r14
0x18000869b  pop     r12
0x18000869d  pop     rdi
0x18000869e  pop     rsi
0x18000869f  pop     rbp
0x1800086a0  pop     rbx
0x1800086a1  retn
```
