# CAviMSRFilter::Save(IMediaPropertyBag *,int,int)

- ea: `0x18011b260`
- end: `0x18011b488`
- name: `?Save@CAviMSRFilter@@UEAAJPEAUIMediaPropertyBag@@HH@Z`
- size: `552`
- prototype: `int(CAviMSRFilter *__hidden this, struct IMediaPropertyBag *, int, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x180004924`
- `0x180038498`
- `0x1800388a0`
- `0x180118cf0`
- `0x18011b260`
- `0x18011b490`
- `0x18011b5e0`
- `0x18014ed5c`
- `0x18015bb98`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18011b451`
- `KERNEL32!LeaveCriticalSection` at `0x18011b451`
- `KERNEL32!EnterCriticalSection` at `0x18011b2a0`
- `KERNEL32!EnterCriticalSection` at `0x18011b2a0`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18011b385`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18011b385`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18011b413`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18011b413`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18011b3ac`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18011b3ac`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18011b3d0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18011b3d0`

## pseudocode

```c
__int64 __fastcall CAviMSRFilter::Save(CAviMSRFilter *this, struct IPropertyBag *a2)
{
  CAviMSRFilter *v2; // r14
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  int v6; // edi
  unsigned __int64 i; // rax
  _DWORD *v8; // rsi
  __int64 v9; // rcx
  SAFEARRAY *v10; // rax
  SAFEARRAY *v11; // r12
  struct IMediaPropertyBagVtbl *lpVtbl; // rax
  unsigned int v14; // [rsp+30h] [rbp-39h] BYREF
  unsigned __int64 v15; // [rsp+38h] [rbp-31h] BYREF
  void *ppvData; // [rsp+40h] [rbp-29h] BYREF
  __int128 v17; // [rsp+48h] [rbp-21h] BYREF
  __int64 v18; // [rsp+58h] [rbp-11h]
  SAFEARRAYBOUND rgsabound; // [rsp+60h] [rbp-9h] BYREF
  wchar_t Buffer[20]; // [rsp+68h] [rbp-1h] BYREF

  v2 = (CAviMSRFilter *)((char *)this - 280);
  v4 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this - 25);
  EnterCriticalSection(v4);
  if ( (int)CAviMSRFilter::CacheInfoChunk(v2) >= 0 )
    SaveInfoChunk(*((const struct _rifflist **)this + 8), a2);
  v6 = 0;
  v14 = 0;
  v15 = 0;
  for ( i = 12; v6 >= 0 && (int)CAviMSRFilter::Search(v2, &v15, 0x50534944u, i, &v14) >= 0; i = v15 + v14 )
  {
    ppvData = 0;
    v6 = CBaseMSRFilter::AllocateAndRead(v2, (unsigned __int8 **)&ppvData, v14, v15);
    if ( v6 >= 0 )
    {
      v8 = ppvData;
      if ( *(_DWORD *)ppvData != 1347635524 || (v9 = *((unsigned int *)ppvData + 1), v9 != v14 - 8LL) )
      {
        operator delete(ppvData);
        v6 = -2147220945;
        break;
      }
      if ( (unsigned int)v9 <= 4 )
      {
        v6 = -2147024883;
      }
      else
      {
        StringCchPrintfW(Buffer, 0x14u, L"DISP/%010d", *((unsigned int *)ppvData + 2));
        rgsabound.lLbound = 0;
        rgsabound.cElements = v8[1] - 4;
        v10 = SafeArrayCreate(0x11u, 1u, &rgsabound);
        v11 = v10;
        if ( v10 )
        {
          ppvData = 0;
          SafeArrayAccessData(v10, &ppvData);
          memcpy_0(ppvData, v8 + 3, (unsigned int)v8[1] - 4LL);
          SafeArrayUnaccessData(v11);
          v18 = 0;
          v17 = 0;
          LOWORD(v17) = 8209;
          lpVtbl = (struct IMediaPropertyBagVtbl *)a2->lpVtbl;
          *((_QWORD *)&v17 + 1) = v11;
          v6 = ((__int64 (__fastcall *)(struct IPropertyBag *, wchar_t *, __int128 *))lpVtbl->Write)(a2, Buffer, &v17);
          SafeArrayDestroy(v11);
        }
        else
        {
          v6 = -2147024882;
        }
      }
      operator delete(v8);
    }
  }
  LeaveCriticalSection(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18011b260  mov     [rsp-8+arg_10], rbx
0x18011b265  mov     [rsp-8+arg_18], rsi
0x18011b26a  push    rbp
0x18011b26b  push    rdi
0x18011b26c  push    r12
0x18011b26e  push    r13
0x18011b270  push    r14
0x18011b272  lea     rbp, [rsp-37h]
0x18011b277  sub     rsp, 0A0h
0x18011b27e  mov     rax, cs:__security_cookie
0x18011b285  xor     rax, rsp
0x18011b288  mov     [rbp+57h+var_30], rax
0x18011b28c  lea     r14, [rcx-118h]
0x18011b293  mov     rdi, rcx
0x18011b296  mov     rbx, [r14+50h]
0x18011b29a  mov     r13, rdx
0x18011b29d  mov     rcx, rbx; lpCriticalSection
0x18011b2a0  call    cs:__imp_EnterCriticalSection
0x18011b2a7  nop     dword ptr [rax+rax+00h]
0x18011b2ac  mov     rcx, r14; this
0x18011b2af  call    ?CacheInfoChunk@CAviMSRFilter@@AEAAJXZ; CAviMSRFilter::CacheInfoChunk(void)
0x18011b2b4  test    eax, eax
0x18011b2b6  js      short loc_18011B2C4
0x18011b2b8  mov     rcx, [rdi+40h]; struct _rifflist *
0x18011b2bc  mov     rdx, r13; struct IPropertyBag *
0x18011b2bf  call    ?SaveInfoChunk@@YAJPEFBU_rifflist@@PEAUIPropertyBag@@@Z; SaveInfoChunk(_rifflist const *,IPropertyBag *)
0x18011b2c4  xor     edi, edi
0x18011b2c6  mov     [rbp+57h+var_90], edi
0x18011b2c9  mov     [rbp+57h+var_88], rdi
0x18011b2cd  lea     eax, [rdi+0Ch]
0x18011b2d0  test    edi, edi
0x18011b2d2  js      loc_18011B44E
0x18011b2d8  lea     rcx, [rbp+57h+var_90]
0x18011b2dc  mov     r9, rax; unsigned __int64
0x18011b2df  mov     [rsp+0C0h+var_A0], rcx; unsigned int *
0x18011b2e4  lea     rdx, [rbp+57h+var_88]; unsigned __int64 *
0x18011b2e8  mov     rcx, r14; this
0x18011b2eb  mov     r8d, 50534944h; unsigned int
0x18011b2f1  call    ?Search@CAviMSRFilter@@AEAAJPEA_KK_KPEAK@Z; CAviMSRFilter::Search(unsigned __int64 *,ulong,unsigned __int64,ulong *)
0x18011b2f6  test    eax, eax
0x18011b2f8  js      loc_18011B44E
0x18011b2fe  mov     r9, [rbp+57h+var_88]; unsigned __int64
0x18011b302  lea     rdx, [rbp+57h+ppvData]; unsigned __int8 **
0x18011b306  mov     r8d, [rbp+57h+var_90]; unsigned int
0x18011b30a  mov     rcx, r14; this
0x18011b30d  mov     [rbp+57h+ppvData], 0
0x18011b315  call    ?AllocateAndRead@CBaseMSRFilter@@IEAAJPEAPEAEK_K@Z; CBaseMSRFilter::AllocateAndRead(uchar * *,ulong,unsigned __int64)
0x18011b31a  mov     edi, eax
0x18011b31c  test    eax, eax
0x18011b31e  js      loc_18011B435
0x18011b324  mov     rsi, [rbp+57h+ppvData]
0x18011b328  cmp     dword ptr [rsi], 50534944h
0x18011b32e  jnz     loc_18011B441
0x18011b334  mov     eax, [rbp+57h+var_90]
0x18011b337  mov     ecx, [rsi+4]
0x18011b33a  sub     rax, 8
0x18011b33e  cmp     rcx, rax
0x18011b341  jnz     loc_18011B441
0x18011b347  cmp     ecx, 4
0x18011b34a  jbe     loc_18011B428
0x18011b350  mov     r9d, [rsi+8]
0x18011b354  lea     r8, aDisp010d; "DISP/%010d"
0x18011b35b  mov     edx, 14h; unsigned __int64
0x18011b360  lea     rcx, [rbp+57h+Buffer]; Buffer
0x18011b364  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18011b369  mov     ecx, 11h; vt
0x18011b36e  mov     [rbp+57h+rgsabound.lLbound], 0
0x18011b375  mov     eax, [rsi+4]
0x18011b378  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x18011b37c  sub     eax, 4
0x18011b37f  mov     [rbp+57h+rgsabound.cElements], eax
0x18011b382  lea     edx, [rcx-10h]; cDims
0x18011b385  call    cs:__imp_SafeArrayCreate
0x18011b38c  nop     dword ptr [rax+rax+00h]
0x18011b391  mov     r12, rax
0x18011b394  test    rax, rax
0x18011b397  jz      loc_18011B421
0x18011b39d  lea     rdx, [rbp+57h+ppvData]; ppvData
0x18011b3a1  mov     [rbp+57h+ppvData], 0
0x18011b3a9  mov     rcx, rax; psa
0x18011b3ac  call    cs:__imp_SafeArrayAccessData
0x18011b3b3  nop     dword ptr [rax+rax+00h]
0x18011b3b8  mov     r8d, [rsi+4]
0x18011b3bc  lea     rdx, [rsi+0Ch]; Src
0x18011b3c0  mov     rcx, [rbp+57h+ppvData]; void *
0x18011b3c4  sub     r8, 4; Size
0x18011b3c8  call    memcpy_0
0x18011b3cd  mov     rcx, r12; psa
0x18011b3d0  call    cs:__imp_SafeArrayUnaccessData
0x18011b3d7  nop     dword ptr [rax+rax+00h]
0x18011b3dc  xor     eax, eax
0x18011b3de  lea     r8, [rbp+57h+var_78]
0x18011b3e2  mov     [rbp+57h+var_68], rax
0x18011b3e6  lea     rdx, [rbp+57h+Buffer]
0x18011b3ea  xorps   xmm0, xmm0
0x18011b3ed  mov     eax, 2011h
0x18011b3f2  movups  [rbp+57h+var_78], xmm0
0x18011b3f6  mov     word ptr [rbp+57h+var_78], ax
0x18011b3fa  mov     rcx, r13
0x18011b3fd  mov     rax, [r13+0]
0x18011b401  mov     qword ptr [rbp+57h+var_78+8], r12
0x18011b405  mov     rax, [rax+20h]
0x18011b409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011b40e  mov     rcx, r12; psa
0x18011b411  mov     edi, eax
0x18011b413  call    cs:__imp_SafeArrayDestroy
0x18011b41a  nop     dword ptr [rax+rax+00h]
0x18011b41f  jmp     short loc_18011B42D
0x18011b421  mov     edi, 8007000Eh
0x18011b426  jmp     short loc_18011B42D
0x18011b428  mov     edi, 8007000Dh
0x18011b42d  mov     rcx, rsi; Block
0x18011b430  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18011b435  mov     eax, [rbp+57h+var_90]
0x18011b438  add     rax, [rbp+57h+var_88]
0x18011b43c  jmp     loc_18011B2D0
0x18011b441  mov     rcx, rsi; Block
0x18011b444  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18011b449  mov     edi, 8004022Fh
0x18011b44e  mov     rcx, rbx; lpCriticalSection
0x18011b451  call    cs:__imp_LeaveCriticalSection
0x18011b458  nop     dword ptr [rax+rax+00h]
0x18011b45d  mov     eax, edi
0x18011b45f  mov     rcx, [rbp+57h+var_30]
0x18011b463  xor     rcx, rsp; StackCookie
0x18011b466  call    __security_check_cookie
0x18011b46b  lea     r11, [rsp+0C0h+var_20]
0x18011b473  mov     rbx, [r11+40h]
0x18011b477  mov     rsi, [r11+48h]
0x18011b47b  mov     rsp, r11
0x18011b47e  pop     r14
0x18011b480  pop     r13
0x18011b482  pop     r12
0x18011b484  pop     rdi
0x18011b485  pop     rbp
0x18011b486  retn
```
