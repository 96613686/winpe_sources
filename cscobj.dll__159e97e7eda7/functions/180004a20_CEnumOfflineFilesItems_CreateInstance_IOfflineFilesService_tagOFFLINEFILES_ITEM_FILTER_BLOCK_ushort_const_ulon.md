# CEnumOfflineFilesItems::CreateInstance(IOfflineFilesService *,tagOFFLINEFILES_ITEM_FILTER_BLOCK *,ushort const *,ulong,ulong,_GUID const &,void * *)

- ea: `0x180004a20`
- end: `0x180004ce1`
- name: `?CreateInstance@CEnumOfflineFilesItems@@SAJPEAUIOfflineFilesService@@PEAUtagOFFLINEFILES_ITEM_FILTER_BLOCK@@PEBGKKAEBU_GUID@@PEAPEAX@Z`
- size: `705`
- prototype: `static int(struct IOfflineFilesService *, struct tagOFFLINEFILES_ITEM_FILTER_BLOCK *, const unsigned __int16 *, unsigned int, unsigned int, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180011c00`

## callees

- `0x180004a20`
- `0x180005410`
- `0x18000b390`
- `0x1800102a8`
- `0x18002ac30`
- `0x18002c010`

## import_xrefs

- `ntdll!RtlpEnsureBufferSize` at `0x180004bc5`
- `ntdll!RtlpEnsureBufferSize` at `0x180004bc5`
- `ntdll!RtlInitUnicodeString` at `0x180004b84`
- `ntdll!RtlInitUnicodeString` at `0x180004b84`

## pseudocode

```c
__int64 __fastcall CEnumOfflineFilesItems::CreateInstance(
        struct IOfflineFilesService *a1,
        struct tagOFFLINEFILES_ITEM_FILTER_BLOCK *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned int a5,
        const struct _GUID *a6,
        void **a7)
{
  char *v11; // rax
  char *v12; // rbx
  IUnknown **v13; // rsi
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 Length; // r8
  int v18; // ecx
  HRESULT v19; // edi
  __int64 v20; // rcx
  PWSTR Buffer; // rdx
  unsigned __int64 v22; // rax
  __int64 v23; // rcx
  unsigned __int64 v24; // r8
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-38h] BYREF

  *a7 = 0;
  v11 = (char *)operator new(0x288u);
  v12 = v11;
  if ( v11 )
  {
    *((_QWORD *)v11 + 3) = 0;
    *((_DWORD *)v11 + 2) = 1;
    *((_QWORD *)v11 + 2) = a1;
    *(_QWORD *)v11 = &CEnumOfflineFilesItems::`vftable';
    v13 = (IUnknown **)(v11 + 24);
    *((_QWORD *)v11 + 71) = v11 + 32;
    *((_QWORD *)v11 + 73) = 520;
    *((_QWORD *)v11 + 72) = v11 + 32;
    *((_QWORD *)v11 + 74) = 520;
    *((_QWORD *)v11 + 70) = v11 + 32;
    if ( v11 != (char *)-32LL )
      *((_WORD *)v11 + 16) = 0;
    *((_DWORD *)v11 + 138) = 34078720;
    *((_DWORD *)v11 + 153) = a5;
    *((_DWORD *)v11 + 152) = a4;
    (*(void (__fastcall **)(struct IOfflineFilesService *, __int64))(*(_QWORD *)a1 + 8LL))(a1, 520);
    *(_OWORD *)(v12 + 616) = 0;
    *(_OWORD *)(v12 + 632) = 0;
    if ( a2 )
    {
      *(_OWORD *)(v12 + 616) = *(_OWORD *)a2;
      *(_OWORD *)(v12 + 632) = *((_OWORD *)a2 + 1);
      if ( *(_QWORD *)a2 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)a2 + 8LL))(*(_QWORD *)a2);
      v14 = *((_QWORD *)a2 + 1);
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
      v15 = *((_QWORD *)a2 + 2);
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
      v16 = *((_QWORD *)a2 + 3);
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
    }
    if ( !a3 )
      goto LABEL_24;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, a3);
    Length = DestinationString.Length;
    *((_WORD *)v12 + 276) = 0;
    if ( (unsigned __int64)(Length + 2) > 0xFFFE )
    {
      v18 = -1073741562;
      goto LABEL_20;
    }
    if ( v12 == (char *)-568LL || (unsigned __int64)(Length + 2) > *((_QWORD *)v12 + 73) )
    {
      if ( RtlpEnsureBufferSize(0, (PRTL_BUFFER)(v12 + 568), Length + 2) < 0 )
      {
        v18 = -1073741801;
LABEL_20:
        v19 = ResultFromNtStatus(v18);
        if ( v19 < 0 )
        {
LABEL_27:
          (*(void (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))(v12);
          return (unsigned int)v19;
        }
LABEL_24:
        v19 = (*(__int64 (__fastcall **)(_QWORD, char *, const unsigned __int16 *, _QWORD, _DWORD, char *))(**((_QWORD **)v12 + 2) + 112LL))(
                *((_QWORD *)v12 + 2),
                v12 + 616,
                a3,
                *((unsigned int *)v12 + 152),
                *((_DWORD *)v12 + 153),
                v12 + 24);
        if ( v19 >= 0 )
        {
          v19 = CscCom_SetClientProxyBlanket(*v13);
          if ( v19 >= 0 )
            v19 = (**(__int64 (__fastcall ***)(char *, const struct _GUID *, void **))v12)(v12, a6, a7);
        }
        goto LABEL_27;
      }
      LOWORD(Length) = DestinationString.Length;
    }
    v20 = *((_QWORD *)v12 + 71);
    Buffer = DestinationString.Buffer;
    v22 = (unsigned __int64)*((unsigned __int16 *)v12 + 276) >> 1;
    *((_QWORD *)v12 + 70) = v20;
    memmove_0((void *)(v20 + 2 * v22), Buffer, (unsigned __int16)Length);
    v23 = *((_QWORD *)v12 + 70);
    v24 = (unsigned __int16)(*((_WORD *)v12 + 276) + DestinationString.Length);
    *((_WORD *)v12 + 276) = v24;
    *((_WORD *)v12 + 277) = v24 + 2;
    *(_WORD *)(v23 + 2 * (v24 >> 1)) = 0;
    goto LABEL_24;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180004a20  mov     [rsp+arg_8], rbx
0x180004a25  mov     [rsp+arg_10], rbp
0x180004a2a  push    rdi
0x180004a2b  push    r12
0x180004a2d  push    r13
0x180004a2f  push    r14
0x180004a31  push    r15
0x180004a33  sub     rsp, 50h
0x180004a37  mov     r15, [rsp+78h+arg_30]
0x180004a3f  mov     r14, rcx
0x180004a42  xor     r13d, r13d
0x180004a45  mov     ecx, 288h; Size
0x180004a4a  mov     ebp, r9d
0x180004a4d  mov     r12, r8
0x180004a50  mov     rdi, rdx
0x180004a53  mov     [r15], r13
0x180004a56  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004a5b  mov     rbx, rax
0x180004a5e  test    rax, rax
0x180004a61  jz      loc_180004CC2
0x180004a67  mov     [rbx+18h], r13
0x180004a6b  lea     rcx, [rbx+20h]
0x180004a6f  mov     dword ptr [rbx+8], 1
0x180004a76  mov     edx, 208h
0x180004a7b  mov     [rbx+10h], r14
0x180004a7f  lea     rax, ??_7CEnumOfflineFilesItems@@6B@; const CEnumOfflineFilesItems::`vftable'
0x180004a86  mov     [rbx], rax
0x180004a89  mov     [rsp+78h+arg_0], rsi
0x180004a91  lea     rsi, [rbx+18h]
0x180004a95  mov     [rbx+238h], rcx
0x180004a9c  mov     [rbx+248h], rdx
0x180004aa3  mov     [rbx+240h], rcx
0x180004aaa  mov     [rbx+250h], rdx
0x180004ab1  mov     [rbx+230h], rcx
0x180004ab8  test    rcx, rcx
0x180004abb  jz      short loc_180004AC1
0x180004abd  mov     [rcx], r13w
0x180004ac1  mov     eax, [rsp+78h+arg_20]
0x180004ac8  mov     rcx, r14
0x180004acb  mov     dword ptr [rbx+228h], 2080000h
0x180004ad5  mov     [rbx+264h], eax
0x180004adb  mov     [rbx+260h], ebp
0x180004ae1  mov     rax, [r14]
0x180004ae4  mov     rax, [rax+8]
0x180004ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aed  xorps   xmm0, xmm0
0x180004af0  movups  xmmword ptr [rbx+268h], xmm0
0x180004af7  movups  xmmword ptr [rbx+278h], xmm0
0x180004afe  test    rdi, rdi
0x180004b01  jz      short loc_180004B6B
0x180004b03  movups  xmm0, xmmword ptr [rdi]
0x180004b06  movups  xmmword ptr [rbx+268h], xmm0
0x180004b0d  movups  xmm1, xmmword ptr [rdi+10h]
0x180004b11  movups  xmmword ptr [rbx+278h], xmm1
0x180004b18  mov     rcx, [rdi]
0x180004b1b  test    rcx, rcx
0x180004b1e  jz      short loc_180004B2C
0x180004b20  mov     rax, [rcx]
0x180004b23  mov     rax, [rax+8]
0x180004b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b2c  mov     rcx, [rdi+8]
0x180004b30  test    rcx, rcx
0x180004b33  jz      short loc_180004B41
0x180004b35  mov     rax, [rcx]
0x180004b38  mov     rax, [rax+8]
0x180004b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b41  mov     rcx, [rdi+10h]
0x180004b45  test    rcx, rcx
0x180004b48  jz      short loc_180004B56
0x180004b4a  mov     rax, [rcx]
0x180004b4d  mov     rax, [rax+8]
0x180004b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b56  mov     rcx, [rdi+18h]
0x180004b5a  test    rcx, rcx
0x180004b5d  jz      short loc_180004B6B
0x180004b5f  mov     rax, [rcx]
0x180004b62  mov     rax, [rax+8]
0x180004b66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b6b  test    r12, r12
0x180004b6e  jz      loc_180004C46
0x180004b74  xorps   xmm0, xmm0
0x180004b77  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x180004b7c  mov     rdx, r12; SourceString
0x180004b7f  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x180004b84  call    cs:__imp_RtlInitUnicodeString
0x180004b8a  movzx   r8d, [rsp+78h+DestinationString.Length]
0x180004b90  mov     [rbx+228h], r13w
0x180004b98  lea     rax, [r8+2]
0x180004b9c  cmp     rax, 0FFFEh
0x180004ba2  jbe     short loc_180004BAB
0x180004ba4  mov     ecx, 0C0000106h
0x180004ba9  jmp     short loc_180004BD4
0x180004bab  lea     rdx, [rbx+238h]; Buffer
0x180004bb2  test    rdx, rdx
0x180004bb5  jz      short loc_180004BC0
0x180004bb7  cmp     rax, [rbx+248h]
0x180004bbe  jbe     short loc_180004BEA
0x180004bc0  mov     r8, rax; RequiredSize
0x180004bc3  xor     ecx, ecx; Flags
0x180004bc5  call    cs:__imp_RtlpEnsureBufferSize
0x180004bcb  test    eax, eax
0x180004bcd  jns     short loc_180004BE4
0x180004bcf  mov     ecx, 0C0000017h; int
0x180004bd4  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x180004bd9  mov     edi, eax
0x180004bdb  test    eax, eax
0x180004bdd  jns     short loc_180004C46
0x180004bdf  jmp     loc_180004CA7
0x180004be4  movzx   r8d, [rsp+78h+DestinationString.Length]
0x180004bea  mov     rcx, [rbx+238h]
0x180004bf1  movzx   eax, word ptr [rbx+228h]
0x180004bf8  mov     rdx, [rsp+78h+DestinationString.Buffer]; Src
0x180004bfd  shr     rax, 1
0x180004c00  mov     [rbx+230h], rcx
0x180004c07  movzx   r8d, r8w; Size
0x180004c0b  lea     rcx, [rcx+rax*2]; void *
0x180004c0f  call    memmove_0
0x180004c14  movzx   eax, [rsp+78h+DestinationString.Length]
0x180004c19  add     ax, [rbx+228h]
0x180004c20  mov     rcx, [rbx+230h]
0x180004c27  movzx   r8d, ax
0x180004c2b  mov     [rbx+228h], r8w
0x180004c33  lea     eax, [r8+2]
0x180004c37  shr     r8, 1
0x180004c3a  mov     [rbx+22Ah], ax
0x180004c41  mov     [rcx+r8*2], r13w
0x180004c46  mov     r8d, [rbx+264h]
0x180004c4d  lea     rdx, [rbx+268h]
0x180004c54  mov     rcx, [rbx+10h]
0x180004c58  mov     r9d, [rbx+260h]
0x180004c5f  mov     [rsp+78h+var_50], rsi
0x180004c64  mov     [rsp+78h+var_58], r8d
0x180004c69  mov     r8, r12
0x180004c6c  mov     rax, [rcx]
0x180004c6f  mov     rax, [rax+70h]
0x180004c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c78  mov     edi, eax
0x180004c7a  test    eax, eax
0x180004c7c  js      short loc_180004CA7
0x180004c7e  mov     rcx, [rsi]; pProxy
0x180004c81  call    ?CscCom_SetClientProxyBlanket@@YAJPEAUIUnknown@@KKH@Z; CscCom_SetClientProxyBlanket(IUnknown *,ulong,ulong,int)
0x180004c86  mov     edi, eax
0x180004c88  test    eax, eax
0x180004c8a  js      short loc_180004CA7
0x180004c8c  mov     rax, [rbx]
0x180004c8f  mov     r8, r15
0x180004c92  mov     rdx, [rsp+78h+arg_28]
0x180004c9a  mov     rcx, rbx
0x180004c9d  mov     rax, [rax]
0x180004ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ca5  mov     edi, eax
0x180004ca7  mov     rax, [rbx]
0x180004caa  mov     rcx, rbx
0x180004cad  mov     rax, [rax+10h]
0x180004cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cb6  mov     rsi, [rsp+78h+arg_0]
0x180004cbe  mov     eax, edi
0x180004cc0  jmp     short loc_180004CC7
0x180004cc2  mov     eax, 8007000Eh
0x180004cc7  lea     r11, [rsp+78h+var_28]
0x180004ccc  mov     rbx, [r11+38h]
0x180004cd0  mov     rbp, [r11+40h]
0x180004cd4  mov     rsp, r11
0x180004cd7  pop     r15
0x180004cd9  pop     r14
0x180004cdb  pop     r13
0x180004cdd  pop     r12
0x180004cdf  pop     rdi
0x180004ce0  retn
```
