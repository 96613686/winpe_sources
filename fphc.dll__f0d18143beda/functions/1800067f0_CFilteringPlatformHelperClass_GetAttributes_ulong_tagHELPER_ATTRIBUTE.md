# CFilteringPlatformHelperClass::GetAttributes(ulong *,tagHELPER_ATTRIBUTE * *)

- ea: `0x1800067f0`
- end: `0x180006968`
- name: `?GetAttributes@CFilteringPlatformHelperClass@@UEAAJPEAKPEAPEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `376`
- prototype: `__int64 __fastcall(CFilteringPlatformHelperClass *__hidden this, unsigned int *, struct tagHELPER_ATTRIBUTE **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800067f0`
- `0x180008a4c`
- `0x1800112f6`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006938`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006941`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006938`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006941`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006866`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800068ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006866`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800068ea`

## pseudocode

```c
__int64 __fastcall CFilteringPlatformHelperClass::GetAttributes(
        CFilteringPlatformHelperClass *this,
        unsigned int *a2,
        LPVOID *a3)
{
  __int128 v5; // xmm6
  unsigned int v6; // ebx
  __int64 v7; // rbx
  struct tagHELPER_ATTRIBUTE *v8; // rax
  _QWORD *v9; // r14
  const unsigned __int16 *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rbp
  unsigned __int16 *v13; // rax
  __int128 v15; // [rsp+20h] [rbp-68h] BYREF
  __int128 v16; // [rsp+30h] [rbp-58h] BYREF

  v5 = *(_OWORD *)((char *)this + 524);
  v16 = v5;
  if ( !a2 || !a3 || *a3 || *a2 )
    return (unsigned int)-2147024809;
  v15 = 0;
  if ( !memcmp_0(&v16, &v15, 0x10u) )
  {
    v6 = 0;
LABEL_22:
    *a3 = 0;
    *a2 = 0;
    return v6;
  }
  v7 = 144;
  v8 = (struct tagHELPER_ATTRIBUTE *)CoTaskMemAlloc(0x90u);
  *a3 = v8;
  if ( v8 )
  {
    do
    {
      LOBYTE(v8->pwszName) = 0;
      v8 = (struct tagHELPER_ATTRIBUTE *)((char *)v8 + 1);
      --v7;
    }
    while ( v7 );
    *((_DWORD *)*a3 + 2) = 11;
    v9 = *a3;
    if ( *a3 )
    {
      v10 = L"rootcauseid";
      v11 = 259;
      do
      {
        if ( !*v10 )
          break;
        ++v10;
        --v11;
      }
      while ( v11 );
      v6 = v11 == 0 ? 0x80070057 : 0;
      v12 = (259 - v11) & -(__int64)(v11 != 0);
      if ( v11 )
      {
        v13 = (unsigned __int16 *)CoTaskMemAlloc(2 * v12 + 2);
        *v9 = v13;
        if ( v13 )
        {
          v6 = StringCchCopyW(v13, v12 + 1, L"rootcauseid");
          if ( (v6 & 0x80000000) == 0 )
          {
            *((_OWORD *)*a3 + 1) = v5;
            *a2 = 1;
            return v6;
          }
        }
        else
        {
          v6 = -2147024882;
        }
      }
    }
    else
    {
      v6 = -2147024809;
    }
    if ( *a3 )
    {
      CoTaskMemFree(*(LPVOID *)*a3);
      CoTaskMemFree(*a3);
      goto LABEL_22;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v6;
}

```

## disassembly

```asm
0x1800067f0  mov     rax, rsp
0x1800067f3  push    rbx
0x1800067f4  push    rbp
0x1800067f5  push    rsi
0x1800067f6  push    rdi
0x1800067f7  push    r14
0x1800067f9  push    r15
0x1800067fb  sub     rsp, 58h
0x1800067ff  movaps  xmmword ptr [rax-48h], xmm6
0x180006803  xor     r15d, r15d
0x180006806  mov     rdi, r8
0x180006809  mov     rsi, rdx
0x18000680c  movups  xmm6, xmmword ptr [rcx+20Ch]
0x180006813  movaps  xmmword ptr [rax-58h], xmm6
0x180006817  test    rdx, rdx
0x18000681a  jz      loc_18000694F
0x180006820  test    r8, r8
0x180006823  jz      loc_18000694F
0x180006829  cmp     [r8], r15
0x18000682c  jnz     loc_18000694F
0x180006832  cmp     [rdx], r15d
0x180006835  jnz     loc_18000694F
0x18000683b  xorps   xmm0, xmm0
0x18000683e  lea     r8d, [r15+10h]; Size
0x180006842  lea     rdx, [rax-68h]; Buf2
0x180006846  lea     rcx, [rax-58h]; Buf1
0x18000684a  movups  xmmword ptr [rax-68h], xmm0
0x18000684e  call    memcmp_0
0x180006853  test    eax, eax
0x180006855  jnz     short loc_18000685F
0x180006857  mov     ebx, r15d
0x18000685a  jmp     loc_180006947
0x18000685f  mov     ebx, 90h
0x180006864  mov     ecx, ebx; cb
0x180006866  call    cs:__imp_CoTaskMemAlloc
0x18000686c  mov     [rdi], rax
0x18000686f  test    rax, rax
0x180006872  jnz     short loc_18000687E
0x180006874  mov     ebx, 8007000Eh
0x180006879  jmp     loc_180006954
0x18000687e  mov     [rax], r15b
0x180006881  inc     rax
0x180006884  sub     rbx, 1
0x180006888  jnz     short loc_18000687E
0x18000688a  mov     rax, [rdi]
0x18000688d  mov     dword ptr [rax+8], 0Bh
0x180006894  mov     r14, [rdi]
0x180006897  test    r14, r14
0x18000689a  jz      loc_180006928
0x1800068a0  mov     edx, 103h
0x1800068a5  lea     rax, aRootcauseid; "rootcauseid"
0x1800068ac  mov     ecx, edx
0x1800068ae  cmp     [rax], r15w
0x1800068b2  jz      short loc_1800068BE
0x1800068b4  add     rax, 2
0x1800068b8  sub     rcx, 1
0x1800068bc  jnz     short loc_1800068AE
0x1800068be  mov     rax, rcx
0x1800068c1  neg     rax
0x1800068c4  mov     rax, rcx
0x1800068c7  sbb     ebx, ebx
0x1800068c9  sub     rdx, rcx
0x1800068cc  not     ebx
0x1800068ce  and     ebx, 80070057h
0x1800068d4  neg     rax
0x1800068d7  sbb     rbp, rbp
0x1800068da  and     rbp, rdx
0x1800068dd  test    rcx, rcx
0x1800068e0  jz      short loc_18000692D
0x1800068e2  lea     rcx, ds:2[rbp*2]; cb
0x1800068ea  call    cs:__imp_CoTaskMemAlloc
0x1800068f0  mov     [r14], rax
0x1800068f3  test    rax, rax
0x1800068f6  jnz     short loc_1800068FF
0x1800068f8  mov     ebx, 8007000Eh
0x1800068fd  jmp     short loc_18000692D
0x1800068ff  lea     rdx, [rbp+1]; unsigned __int64
0x180006903  mov     rcx, rax; unsigned __int16 *
0x180006906  lea     r8, aRootcauseid; "rootcauseid"
0x18000690d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180006912  mov     ebx, eax
0x180006914  test    eax, eax
0x180006916  js      short loc_18000692D
0x180006918  mov     rax, [rdi]
0x18000691b  movdqu  xmmword ptr [rax+10h], xmm6
0x180006920  mov     dword ptr [rsi], 1
0x180006926  jmp     short loc_180006954
0x180006928  mov     ebx, 80070057h
0x18000692d  mov     rcx, [rdi]
0x180006930  test    rcx, rcx
0x180006933  jz      short loc_180006954
0x180006935  mov     rcx, [rcx]; pv
0x180006938  call    cs:__imp_CoTaskMemFree
0x18000693e  mov     rcx, [rdi]; pv
0x180006941  call    cs:__imp_CoTaskMemFree
0x180006947  mov     [rdi], r15
0x18000694a  mov     [rsi], r15d
0x18000694d  jmp     short loc_180006954
0x18000694f  mov     ebx, 80070057h
0x180006954  movaps  xmm6, [rsp+88h+var_48]
0x180006959  mov     eax, ebx
0x18000695b  add     rsp, 58h
0x18000695f  pop     r15
0x180006961  pop     r14
0x180006963  pop     rdi
0x180006964  pop     rsi
0x180006965  pop     rbp
0x180006966  pop     rbx
0x180006967  retn
```
