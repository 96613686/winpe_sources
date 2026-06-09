# CEnhancedStorageAct::GetSilos(IEnhancedStorageSilo * * *,ulong *)

- ea: `0x180002a60`
- end: `0x180002be5`
- name: `?GetSilos@CEnhancedStorageAct@@UEAAJPEAPEAPEAUIEnhancedStorageSilo@@PEAK@Z`
- size: `389`
- prototype: `__int64 __fastcall(CEnhancedStorageAct *__hidden this, struct IEnhancedStorageSilo ***, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002190`
- `0x180002a60`
- `0x180003c54`
- `0x180003ce0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002aa0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002aa0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002b88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002b88`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageAct::GetSilos(
        CEnhancedStorageAct *this,
        struct IEnhancedStorageSilo ***a2,
        unsigned int *a3)
{
  unsigned int v6; // ebp
  __int64 v7; // rsi
  struct IEnhancedStorageSilo **v8; // rdi
  int v9; // ebx
  _QWORD *v10; // rax
  int v11; // eax
  __int64 i; // rbp
  struct IEnhancedStorageSilo *v14; // [rsp+70h] [rbp+8h] BYREF

  v14 = 0;
  if ( a2 && a3 )
  {
    v6 = *((_DWORD *)this + 20);
    v7 = 0;
    v8 = (struct IEnhancedStorageSilo **)CoTaskMemAlloc(8LL * v6);
    if ( v8 )
    {
      v9 = 0;
      while ( (unsigned int)v7 < v6 )
      {
        v10 = (_QWORD *)ATL::CAtlArray<ATL::CComObject<CEnhancedStorageSilo> *,ATL::CElementTraits<ATL::CComObject<CEnhancedStorageSilo> *>>::operator[](
                          (char *)this + 72,
                          (unsigned int)v7);
        v11 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct IEnhancedStorageSilo **))*v10)(
                *v10,
                &IID_IEnhancedStorageSilo,
                &v14);
        v9 = v11;
        if ( v11 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              45,
              WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids,
              (unsigned int)v11);
          goto LABEL_15;
        }
        v8[v7] = v14;
        v7 = (unsigned int)(v7 + 1);
      }
      if ( v9 < 0 )
        goto LABEL_15;
      *a2 = v8;
      *a3 = v6;
    }
    else
    {
      v9 = -2147024882;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_15:
        for ( i = 0; (unsigned int)i < (unsigned int)v7; i = (unsigned int)(i + 1) )
          ((void (__fastcall *)(struct IEnhancedStorageSilo *))v8[i]->lpVtbl->Release)(v8[i]);
        if ( v8 )
          CoTaskMemFree(v8);
      }
      else
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids, 2147942414LL);
      }
    }
    return (unsigned int)v9;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids,
        "pppIEnhancedStorageSilos && pcEnhancedStorageSilos");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180002a60  push    rbx
0x180002a62  push    rbp
0x180002a63  push    rsi
0x180002a64  push    rdi
0x180002a65  push    r12
0x180002a67  push    r13
0x180002a69  push    r14
0x180002a6b  push    r15
0x180002a6d  sub     rsp, 28h
0x180002a71  mov     [rsp+68h+arg_0], 0
0x180002a7a  mov     r14, r8
0x180002a7d  mov     r15, rdx
0x180002a80  mov     r13, rcx
0x180002a83  test    rdx, rdx
0x180002a86  jz      loc_180002B9A
0x180002a8c  test    r8, r8
0x180002a8f  jz      loc_180002B9A
0x180002a95  mov     ebp, [rcx+50h]
0x180002a98  xor     esi, esi
0x180002a9a  mov     ecx, ebp
0x180002a9c  shl     rcx, 3; cb
0x180002aa0  call    cs:__imp_CoTaskMemAlloc
0x180002aa6  mov     rdi, rax
0x180002aa9  test    rax, rax
0x180002aac  jnz     short loc_180002AEF
0x180002aae  mov     ebx, 8007000Eh
0x180002ab3  mov     rcx, cs:WPP_GLOBAL_Control
0x180002aba  lea     rdx, WPP_GLOBAL_Control
0x180002ac1  cmp     rcx, rdx
0x180002ac4  jz      loc_180002B64
0x180002aca  test    byte ptr [rcx+1Ch], 2
0x180002ace  jz      loc_180002B64
0x180002ad4  mov     rcx, [rcx+10h]
0x180002ad8  lea     edx, [rsi+2Ch]
0x180002adb  mov     r9d, ebx
0x180002ade  lea     r8, WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids
0x180002ae5  call    WPP_SF_d
0x180002aea  jmp     loc_180002B96
0x180002aef  xor     ebx, ebx
0x180002af1  cmp     esi, ebp
0x180002af3  jnb     short loc_180002B60
0x180002af5  lea     rcx, [r13+48h]
0x180002af9  mov     edx, esi
0x180002afb  call    ??A?$CAtlArray@PEAV?$CComObject@VCEnhancedStorageSilo@@@ATL@@V?$CElementTraits@PEAV?$CComObject@VCEnhancedStorageSilo@@@ATL@@@2@@ATL@@QEAAAEAPEAV?$CComObject@VCEnhancedStorageSilo@@@1@_K@Z; ATL::CAtlArray<ATL::CComObject<CEnhancedStorageSilo> *,ATL::CElementTraits<ATL::CComObject<CEnhancedStorageSilo> *>>::operator[](unsigned __int64)
0x180002b00  lea     r8, [rsp+68h+arg_0]
0x180002b05  lea     rdx, IID_IEnhancedStorageSilo
0x180002b0c  mov     rcx, [rax]
0x180002b0f  mov     rax, [rcx]
0x180002b12  mov     rax, [rax]
0x180002b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b1a  mov     ebx, eax
0x180002b1c  test    eax, eax
0x180002b1e  js      short loc_180002B2D
0x180002b20  mov     rcx, [rsp+68h+arg_0]
0x180002b25  mov     [rdi+rsi*8], rcx
0x180002b29  inc     esi
0x180002b2b  jmp     short loc_180002AF1
0x180002b2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b34  lea     rdx, WPP_GLOBAL_Control
0x180002b3b  cmp     rcx, rdx
0x180002b3e  jz      short loc_180002B64
0x180002b40  test    byte ptr [rcx+1Ch], 2
0x180002b44  jz      short loc_180002B64
0x180002b46  mov     rcx, [rcx+10h]
0x180002b4a  lea     r8, WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids
0x180002b51  mov     edx, 2Dh ; '-'
0x180002b56  mov     r9d, eax
0x180002b59  call    WPP_SF_d
0x180002b5e  jmp     short loc_180002B64
0x180002b60  test    ebx, ebx
0x180002b62  jns     short loc_180002B90
0x180002b64  xor     ebp, ebp
0x180002b66  test    esi, esi
0x180002b68  jz      short loc_180002B80
0x180002b6a  mov     rcx, [rdi+rbp*8]
0x180002b6e  mov     rax, [rcx]
0x180002b71  mov     rax, [rax+10h]
0x180002b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b7a  inc     ebp
0x180002b7c  cmp     ebp, esi
0x180002b7e  jb      short loc_180002B6A
0x180002b80  test    rdi, rdi
0x180002b83  jz      short loc_180002B96
0x180002b85  mov     rcx, rdi; pv
0x180002b88  call    cs:__imp_CoTaskMemFree
0x180002b8e  jmp     short loc_180002B96
0x180002b90  mov     [r15], rdi
0x180002b93  mov     [r14], ebp
0x180002b96  mov     eax, ebx
0x180002b98  jmp     short loc_180002BD4
0x180002b9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ba1  lea     rdx, WPP_GLOBAL_Control
0x180002ba8  cmp     rcx, rdx
0x180002bab  jz      short loc_180002BCF
0x180002bad  test    byte ptr [rcx+1Ch], 2
0x180002bb1  jz      short loc_180002BCF
0x180002bb3  mov     rcx, [rcx+10h]
0x180002bb7  lea     r9, aPppienhancedst_0; "pppIEnhancedStorageSilos && pcEnhancedS"...
0x180002bbe  mov     edx, 2Bh ; '+'
0x180002bc3  lea     r8, WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids
0x180002bca  call    WPP_SF_s
0x180002bcf  mov     eax, 80070057h
0x180002bd4  add     rsp, 28h
0x180002bd8  pop     r15
0x180002bda  pop     r14
0x180002bdc  pop     r13
0x180002bde  pop     r12
0x180002be0  pop     rdi
0x180002be1  pop     rsi
0x180002be2  pop     rbp
0x180002be3  pop     rbx
0x180002be4  retn
```
