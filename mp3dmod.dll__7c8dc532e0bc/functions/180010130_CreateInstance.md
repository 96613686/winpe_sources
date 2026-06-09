# CreateInstance

- ea: `0x180010130`
- end: `0x1800101c8`
- name: `CreateInstance`
- size: `152`
- prototype: `__int64 __fastcall(void *Buf2, struct IUnknown *, struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000c590`
- `0x18000c5c0`
- `0x180010130`
- `0x1800114a5`

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
0x180010130  push    rbx
0x180010132  push    rbp
0x180010133  push    rsi
0x180010134  push    rdi
0x180010135  push    r14
0x180010137  push    r15
0x180010139  sub     rsp, 48h
0x18001013d  mov     rdi, r9
0x180010140  mov     rbp, r8
0x180010143  mov     r14, rdx
0x180010146  mov     r15, rcx
0x180010149  test    r9, r9
0x18001014c  jnz     short loc_180010155
0x18001014e  mov     eax, 80004003h
0x180010153  jmp     short loc_1800101BB
0x180010155  mov     qword ptr [r9], 0
0x18001015c  xor     ebx, ebx
0x18001015e  cmp     ebx, 1
0x180010161  jge     short loc_1800101B6
0x180010163  lea     rcx, ?g_ComClassTemplates@@3PAUCComClassTemplate@@A; CComClassTemplate near * g_ComClassTemplates
0x18001016a  movsxd  rsi, ebx
0x18001016d  shl     rsi, 4
0x180010171  mov     r8d, 10h; Size
0x180010177  add     rsi, rcx
0x18001017a  mov     rdx, r15; Buf2
0x18001017d  mov     rcx, [rsi]; Buf1
0x180010180  call    memcmp_0
0x180010185  test    eax, eax
0x180010187  jz      short loc_18001018D
0x180010189  inc     ebx
0x18001018b  jmp     short loc_18001015E
0x18001018d  mov     rdx, rsi; struct CComClassTemplate *
0x180010190  lea     rcx, [rsp+78h+var_58]; this
0x180010195  call    ??0CClassFactory@@QEAA@PEBUCComClassTemplate@@@Z; CClassFactory::CClassFactory(CComClassTemplate const *)
0x18001019a  mov     r9, rdi; void **
0x18001019d  lea     rcx, [rsp+78h+var_58]; this
0x1800101a2  mov     r8, rbp; struct _GUID *
0x1800101a5  mov     rdx, r14; struct IUnknown *
0x1800101a8  call    ?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)
0x1800101ad  lock dec cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x1800101b4  jmp     short loc_1800101BB
0x1800101b6  mov     eax, 80040111h
0x1800101bb  add     rsp, 48h
0x1800101bf  pop     r15
0x1800101c1  pop     r14
0x1800101c3  pop     rdi
0x1800101c4  pop     rsi
0x1800101c5  pop     rbp
0x1800101c6  pop     rbx
0x1800101c7  retn
```
