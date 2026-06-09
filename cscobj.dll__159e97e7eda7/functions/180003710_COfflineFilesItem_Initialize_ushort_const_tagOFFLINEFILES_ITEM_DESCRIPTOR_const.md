# COfflineFilesItem::_Initialize(ushort const *,tagOFFLINEFILES_ITEM_DESCRIPTOR const &)

- ea: `0x180003710`
- end: `0x180003948`
- name: `?_Initialize@COfflineFilesItem@@IEAAJPEBGAEBUtagOFFLINEFILES_ITEM_DESCRIPTOR@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(COfflineFilesItem *__hidden this, const unsigned __int16 *, const struct tagOFFLINEFILES_ITEM_DESCRIPTOR *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800020a0`
- `0x180002df0`

## callees

- `0x180003600`
- `0x180003710`
- `0x1800102a8`
- `0x180011d08`
- `0x180011e04`
- `0x18002ac30`

## import_xrefs

- `ntdll!RtlpEnsureBufferSize` at `0x180003776`
- `ntdll!RtlpEnsureBufferSize` at `0x1800038a9`
- `ntdll!RtlpEnsureBufferSize` at `0x180003776`
- `ntdll!RtlpEnsureBufferSize` at `0x1800038a9`
- `ntdll!RtlInitUnicodeString` at `0x180003740`
- `ntdll!RtlInitUnicodeString` at `0x180003877`
- `ntdll!RtlInitUnicodeString` at `0x180003740`
- `ntdll!RtlInitUnicodeString` at `0x180003877`

## pseudocode

```c
__int64 __fastcall COfflineFilesItem::_Initialize(
        COfflineFilesItem *this,
        const unsigned __int16 *a2,
        const struct tagOFFLINEFILES_ITEM_DESCRIPTOR *a3)
{
  int v5; // edi
  int v6; // ebp
  __int64 v7; // r9
  SIZE_T v8; // r8
  size_t Length; // r8
  __int64 v10; // rcx
  PWSTR Buffer; // rdx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rcx
  char *v14; // rcx
  const struct tagOFFLINEFILES_ITEM_DESCRIPTOR *v15; // rax
  __int64 v16; // rdx
  __int128 v17; // xmm0
  int v19; // ecx
  const unsigned __int16 *NextComponent; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF

  if ( a2 && *a2 )
  {
    DestinationString = 0;
    v6 = 1;
    RtlInitUnicodeString(&DestinationString, a2);
    Length = DestinationString.Length;
    v5 = 0;
    *((_WORD *)this + 272) = 0;
    if ( Length + 2 > 0xFFFE )
    {
      v19 = -1073741562;
    }
    else
    {
      if ( this != (COfflineFilesItem *)-560LL && Length + 2 <= *((_QWORD *)this + 72) )
        goto LABEL_18;
      if ( RtlpEnsureBufferSize(0, (PRTL_BUFFER)((char *)this + 560), Length + 2) >= 0 )
      {
        LOWORD(Length) = DestinationString.Length;
LABEL_18:
        Length = (unsigned __int16)Length;
        goto LABEL_7;
      }
      v19 = -1073741801;
    }
LABEL_25:
    v5 = ResultFromNtStatus(v19);
    goto LABEL_8;
  }
  v5 = 0;
  v6 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\\\");
  v7 = DestinationString.Length;
  *((_WORD *)this + 272) = 0;
  v8 = v7 + 2;
  if ( (unsigned __int64)(v7 + 2) > 0xFFFE )
  {
    v19 = -1073741562;
    goto LABEL_25;
  }
  if ( this == (COfflineFilesItem *)-560LL || v8 > *((_QWORD *)this + 72) )
  {
    if ( RtlpEnsureBufferSize(0, (PRTL_BUFFER)((char *)this + 560), v8) < 0 )
    {
      v19 = -1073741801;
      goto LABEL_25;
    }
    LOWORD(v7) = DestinationString.Length;
  }
  Length = (unsigned __int16)v7;
LABEL_7:
  v10 = *((_QWORD *)this + 70);
  Buffer = DestinationString.Buffer;
  v12 = (unsigned __int64)*((unsigned __int16 *)this + 272) >> 1;
  *((_QWORD *)this + 69) = v10;
  memmove_0((void *)(v10 + 2 * v12), Buffer, Length);
  v13 = (unsigned __int16)(*((_WORD *)this + 272) + DestinationString.Length);
  *((_WORD *)this + 272) = v13;
  *((_WORD *)this + 273) = v13 + 2;
  *(_WORD *)(*((_QWORD *)this + 69) + 2 * (v13 >> 1)) = 0;
LABEL_8:
  if ( v5 < 0 )
    return (unsigned int)v5;
  v14 = (char *)this + 600;
  v15 = a3;
  v16 = 6;
  do
  {
    v14 += 128;
    v17 = *(_OWORD *)v15;
    v15 = (const struct tagOFFLINEFILES_ITEM_DESCRIPTOR *)((char *)v15 + 128);
    *((_OWORD *)v14 - 8) = v17;
    *((_OWORD *)v14 - 7) = *((_OWORD *)v15 - 7);
    *((_OWORD *)v14 - 6) = *((_OWORD *)v15 - 6);
    *((_OWORD *)v14 - 5) = *((_OWORD *)v15 - 5);
    *((_OWORD *)v14 - 4) = *((_OWORD *)v15 - 4);
    *((_OWORD *)v14 - 3) = *((_OWORD *)v15 - 3);
    *((_OWORD *)v14 - 2) = *((_OWORD *)v15 - 2);
    *((_OWORD *)v14 - 1) = *((_OWORD *)v15 - 1);
    --v16;
  }
  while ( v16 );
  if ( v6 || !(unsigned int)CscPath_IsUNCServer((const unsigned __int16 *)a3 + 107) )
    return (unsigned int)v5;
  NextComponent = CscPath_FindNextComponent((const unsigned __int16 *)this + 407);
  return StringCchCopyW((unsigned __int16 *)this + 407, 0x105u, NextComponent);
}

```

## disassembly

```asm
0x180003710  push    rbx
0x180003712  push    rbp
0x180003713  push    rsi
0x180003714  push    rdi
0x180003715  sub     rsp, 38h
0x180003719  mov     rsi, r8
0x18000371c  mov     rbx, rcx
0x18000371f  test    rdx, rdx
0x180003722  jnz     loc_18000385B
0x180003728  xorps   xmm0, xmm0
0x18000372b  lea     rdx, SourceString; "\\\\"
0x180003732  xor     edi, edi
0x180003734  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x180003739  mov     ebp, edi
0x18000373b  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x180003740  call    cs:__imp_RtlInitUnicodeString
0x180003746  movzx   r9d, [rsp+58h+DestinationString.Length]
0x18000374c  mov     [rbx+220h], di
0x180003753  lea     r8, [r9+2]; RequiredSize
0x180003757  cmp     r8, 0FFFEh
0x18000375e  ja      loc_1800038F7
0x180003764  lea     rdx, [rbx+230h]; Buffer
0x18000376b  test    rdx, rdx
0x18000376e  jnz     loc_1800038C2
0x180003774  xor     ecx, ecx; Flags
0x180003776  call    cs:__imp_RtlpEnsureBufferSize
0x18000377c  test    eax, eax
0x18000377e  js      loc_1800038FE
0x180003784  movzx   r9d, [rsp+58h+DestinationString.Length]
0x18000378a  movzx   r8d, r9w; Size
0x18000378e  movzx   eax, word ptr [rbx+220h]
0x180003795  mov     rcx, [rbx+230h]
0x18000379c  mov     rdx, [rsp+58h+DestinationString.Buffer]; Src
0x1800037a1  shr     rax, 1
0x1800037a4  mov     [rbx+228h], rcx
0x1800037ab  lea     rcx, [rcx+rax*2]; void *
0x1800037af  call    memmove_0
0x1800037b4  movzx   eax, [rsp+58h+DestinationString.Length]
0x1800037b9  add     ax, [rbx+220h]
0x1800037c0  movzx   ecx, ax
0x1800037c3  mov     [rbx+220h], cx
0x1800037ca  lea     eax, [rcx+2]
0x1800037cd  shr     rcx, 1
0x1800037d0  mov     [rbx+222h], ax
0x1800037d7  mov     rax, [rbx+228h]
0x1800037de  mov     [rax+rcx*2], di
0x1800037e2  test    edi, edi
0x1800037e4  js      short loc_180003850
0x1800037e6  lea     rcx, [rbx+258h]
0x1800037ed  mov     rax, rsi
0x1800037f0  mov     edx, 6
0x1800037f5  lea     rcx, [rcx+80h]
0x1800037fc  movups  xmm0, xmmword ptr [rax]
0x1800037ff  lea     rax, [rax+80h]
0x180003806  movups  xmmword ptr [rcx-80h], xmm0
0x18000380a  movups  xmm1, xmmword ptr [rax-70h]
0x18000380e  movups  xmmword ptr [rcx-70h], xmm1
0x180003812  movups  xmm0, xmmword ptr [rax-60h]
0x180003816  movups  xmmword ptr [rcx-60h], xmm0
0x18000381a  movups  xmm1, xmmword ptr [rax-50h]
0x18000381e  movups  xmmword ptr [rcx-50h], xmm1
0x180003822  movups  xmm0, xmmword ptr [rax-40h]
0x180003826  movups  xmmword ptr [rcx-40h], xmm0
0x18000382a  movups  xmm1, xmmword ptr [rax-30h]
0x18000382e  movups  xmmword ptr [rcx-30h], xmm1
0x180003832  movups  xmm0, xmmword ptr [rax-20h]
0x180003836  movups  xmmword ptr [rcx-20h], xmm0
0x18000383a  movups  xmm1, xmmword ptr [rax-10h]
0x18000383e  movups  xmmword ptr [rcx-10h], xmm1
0x180003842  sub     rdx, 1; SourceString
0x180003846  jnz     short loc_1800037F5
0x180003848  test    ebp, ebp
0x18000384a  jz      loc_18000390F
0x180003850  mov     eax, edi
0x180003852  add     rsp, 38h
0x180003856  pop     rdi
0x180003857  pop     rsi
0x180003858  pop     rbp
0x180003859  pop     rbx
0x18000385a  retn
0x18000385b  cmp     word ptr [rdx], 0
0x18000385f  jz      loc_180003728
0x180003865  xorps   xmm0, xmm0
0x180003868  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x18000386d  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x180003872  mov     ebp, 1
0x180003877  call    cs:__imp_RtlInitUnicodeString
0x18000387d  movzx   r8d, [rsp+58h+DestinationString.Length]
0x180003883  xor     edi, edi
0x180003885  mov     [rbx+220h], di
0x18000388c  lea     rax, [r8+2]
0x180003890  cmp     rax, 0FFFEh
0x180003896  ja      short loc_1800038DF
0x180003898  lea     rdx, [rbx+230h]; Buffer
0x18000389f  test    rdx, rdx
0x1800038a2  jnz     short loc_1800038D4
0x1800038a4  mov     r8, rax; RequiredSize
0x1800038a7  xor     ecx, ecx; Flags
0x1800038a9  call    cs:__imp_RtlpEnsureBufferSize
0x1800038af  test    eax, eax
0x1800038b1  js      short loc_1800038E6
0x1800038b3  movzx   r8d, [rsp+58h+DestinationString.Length]
0x1800038b9  movzx   r8d, r8w
0x1800038bd  jmp     loc_18000378E
0x1800038c2  cmp     r8, [rbx+240h]
0x1800038c9  jbe     loc_18000378A
0x1800038cf  jmp     loc_180003774
0x1800038d4  cmp     rax, [rbx+240h]
0x1800038db  jbe     short loc_1800038B9
0x1800038dd  jmp     short loc_1800038A4
0x1800038df  mov     ecx, 0C0000106h
0x1800038e4  jmp     short loc_1800038EB
0x1800038e6  mov     ecx, 0C0000017h; int
0x1800038eb  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x1800038f0  mov     edi, eax
0x1800038f2  jmp     loc_1800037E2
0x1800038f7  mov     ecx, 0C0000106h
0x1800038fc  jmp     short loc_180003903
0x1800038fe  mov     ecx, 0C0000017h; int
0x180003903  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x180003908  mov     edi, eax
0x18000390a  jmp     loc_1800037E2
0x18000390f  lea     rcx, [rsi+0D6h]; unsigned __int16 *
0x180003916  call    ?CscPath_IsUNCServer@@YAHPEBG@Z; CscPath_IsUNCServer(ushort const *)
0x18000391b  test    eax, eax
0x18000391d  jz      loc_180003850
0x180003923  lea     rcx, [rbx+32Eh]; unsigned __int16 *
0x18000392a  call    ?CscPath_FindNextComponent@@YAPEAGPEBG@Z; CscPath_FindNextComponent(ushort const *)
0x18000392f  mov     r8, rax; unsigned __int16 *
0x180003932  lea     rcx, [rbx+32Eh]; unsigned __int16 *
0x180003939  mov     edx, 105h; unsigned __int64
0x18000393e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003943  jmp     loc_180003852
```
