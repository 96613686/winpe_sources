# CreateInstance

- ea: `0x18000f070`
- end: `0x18000f108`
- name: `CreateInstance`
- size: `152`
- prototype: `__int64 __fastcall(void *Buf2, struct IUnknown *, struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800087d0`
- `0x180008d10`
- `0x18000f070`
- `0x180029fb4`

## pseudocode

```c
__int64 __fastcall CreateInstance(void *Buf2, struct IUnknown *a2, struct _GUID *a3, void **a4)
{
  __int64 result; // rax
  int i; // ebx
  const struct CComClassTemplate *v10; // rsi
  _BYTE v11[88]; // [rsp+20h] [rbp-58h] BYREF

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  for ( i = 0; i < 1; ++i )
  {
    v10 = (const struct CComClassTemplate *)(&g_ComClassTemplates + 2 * i);
    if ( !memcmp_0(*(const void **)v10, Buf2, 0x10u) )
    {
      CClassFactory::CClassFactory((CClassFactory *)v11, v10);
      result = CClassFactory::CreateInstance((CClassFactory *)v11, a2, a3, a4);
      _InterlockedDecrement(&g_cActiveObjects);
      return result;
    }
  }
  return 2147746065LL;
}

```

## disassembly

```asm
0x18000f070  push    rbx
0x18000f072  push    rbp
0x18000f073  push    rsi
0x18000f074  push    rdi
0x18000f075  push    r14
0x18000f077  push    r15
0x18000f079  sub     rsp, 48h
0x18000f07d  mov     rdi, r9
0x18000f080  mov     rbp, r8
0x18000f083  mov     r14, rdx
0x18000f086  mov     r15, rcx
0x18000f089  test    r9, r9
0x18000f08c  jnz     short loc_18000F095
0x18000f08e  mov     eax, 80004003h
0x18000f093  jmp     short loc_18000F0FB
0x18000f095  mov     qword ptr [r9], 0
0x18000f09c  xor     ebx, ebx
0x18000f09e  cmp     ebx, 1
0x18000f0a1  jge     short loc_18000F0F6
0x18000f0a3  lea     rcx, ?g_ComClassTemplates@@3PAUCComClassTemplate@@A; CComClassTemplate near * g_ComClassTemplates
0x18000f0aa  movsxd  rsi, ebx
0x18000f0ad  shl     rsi, 4
0x18000f0b1  mov     r8d, 10h; Size
0x18000f0b7  add     rsi, rcx
0x18000f0ba  mov     rdx, r15; Buf2
0x18000f0bd  mov     rcx, [rsi]; Buf1
0x18000f0c0  call    memcmp_0
0x18000f0c5  test    eax, eax
0x18000f0c7  jz      short loc_18000F0CD
0x18000f0c9  inc     ebx
0x18000f0cb  jmp     short loc_18000F09E
0x18000f0cd  mov     rdx, rsi; struct CComClassTemplate *
0x18000f0d0  lea     rcx, [rsp+78h+var_58]; this
0x18000f0d5  call    ??0CClassFactory@@QEAA@PEBUCComClassTemplate@@@Z; CClassFactory::CClassFactory(CComClassTemplate const *)
0x18000f0da  mov     r9, rdi; void **
0x18000f0dd  lea     rcx, [rsp+78h+var_58]; this
0x18000f0e2  mov     r8, rbp; struct _GUID *
0x18000f0e5  mov     rdx, r14; struct IUnknown *
0x18000f0e8  call    ?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)
0x18000f0ed  lock dec cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x18000f0f4  jmp     short loc_18000F0FB
0x18000f0f6  mov     eax, 80040111h
0x18000f0fb  add     rsp, 48h
0x18000f0ff  pop     r15
0x18000f101  pop     r14
0x18000f103  pop     rdi
0x18000f104  pop     rsi
0x18000f105  pop     rbp
0x18000f106  pop     rbx
0x18000f107  retn
```
