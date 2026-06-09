# SPSslGeneratePreMasterKey

- ea: `0x180013740`
- end: `0x18001394a`
- name: `SPSslGeneratePreMasterKey`
- size: `522`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *, unsigned int, unsigned int, __int64, __int64, int, __int64, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180003ef0`
- `0x180005e50`
- `0x1800068e0`
- `0x180007940`
- `0x18000b594`
- `0x18000b654`
- `0x180012d98`
- `0x180013740`

## string_xrefs

- `0x180013789`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800137cb`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180013923`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslGeneratePreMasterKey(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        int a8,
        __int64 a9,
        int a10)
{
  int v13; // edx
  int v14; // r9d
  unsigned int v15; // ebx
  __int64 v16; // r9
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rsi
  __int64 v20; // rcx
  __int64 v21; // rdi
  __int64 v22; // rcx
  __int64 v23; // r9
  int v24; // eax

  if ( !SslpValidateProvHandle() )
  {
    v15 = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        97);
    return v15;
  }
  if ( !a3 )
  {
    v16 = 2664;
LABEL_7:
    v15 = -2146893785;
    v17 = 2148073511LL;
LABEL_8:
    DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v16);
    return v15;
  }
  if ( a4 != 65277 && (unsigned int)(v14 - 768) > 3 && a4 != 65279 )
  {
    v15 = -2146893783;
    v16 = 2676;
    v17 = 2148073513LL;
    goto LABEL_8;
  }
  v18 = LookupCipherSuite(a4, a5);
  v19 = v18;
  if ( v18 && *(_DWORD *)(v18 + 100) == 1 )
  {
    if ( !a6 )
    {
      v16 = 2691;
      goto LABEL_7;
    }
    if ( (a10 & 0xFFFFFFFE) != 0 )
    {
      v15 = -2146893815;
      v16 = 2698;
      v17 = 2148073481LL;
      goto LABEL_8;
    }
    v21 = SafeAllocaAllocateFromHeap(60);
    if ( v21 )
    {
      *(_OWORD *)v21 = 0;
      *(_OWORD *)(v21 + 16) = 0;
      *(_OWORD *)(v21 + 32) = 0;
      *(_OWORD *)(v21 + 44) = 0;
      *(_DWORD *)v21 = 60;
      *(_DWORD *)(v21 + 4) = 1936944183;
      *(_DWORD *)(v21 + 8) = a4;
      v24 = TlsEncryptPreMasterKey(v20, v21, a2, a6, *(_DWORD *)(v19 + 112), a7, a8, a9);
      v15 = v24;
      if ( v24 >= 0 )
      {
        *a3 = v21;
        return v15;
      }
      v22 = (unsigned int)v24;
      v23 = 2729;
    }
    else
    {
      v15 = -2146893810;
      v22 = 2148073486LL;
      v23 = 2709;
    }
  }
  else
  {
    v21 = 0;
    v15 = -2146893783;
    v22 = 2148073513LL;
    v23 = 2684;
  }
  DebugTraceError(v22, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v23);
  if ( v21 )
    MSCryptFree(v21);
  return v15;
}

```

## disassembly

```asm
0x180013740  push    rbx
0x180013742  push    rsi
0x180013743  push    rdi
0x180013744  push    r14
0x180013746  push    r15
0x180013748  sub     rsp, 40h
0x18001374c  mov     ebx, r9d
0x18001374f  mov     r14, r8
0x180013752  mov     r15, rdx
0x180013755  call    SslpValidateProvHandle
0x18001375a  test    rax, rax
0x18001375d  jnz     short loc_1800137B6
0x18001375f  mov     ebx, 80090026h
0x180013764  mov     rcx, cs:WPP_GLOBAL_Control
0x18001376b  lea     rax, WPP_GLOBAL_Control
0x180013772  cmp     rcx, rax
0x180013775  jz      loc_18001393C
0x18001377b  test    byte ptr [rcx+1Ch], 1
0x18001377f  jz      loc_18001393C
0x180013785  mov     rcx, [rcx+10h]
0x180013789  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013790  mov     [rsp+68h+var_38], 0A61h
0x180013798  lea     r9, aStatus; "Status"
0x18001379f  mov     [rsp+68h+var_40], r8
0x1800137a4  mov     [rsp+68h+var_48], 80090026h
0x1800137ac  call    WPP_SF_sDsd
0x1800137b1  jmp     loc_18001393C
0x1800137b6  test    r14, r14
0x1800137b9  jnz     short loc_1800137E3
0x1800137bb  mov     r9d, 0A68h
0x1800137c1  mov     ebx, 80090027h
0x1800137c6  mov     ecx, 80090027h
0x1800137cb  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800137d2  lea     rdx, aStatus; "Status"
0x1800137d9  call    DebugTraceError
0x1800137de  jmp     loc_18001393C
0x1800137e3  cmp     ebx, 0FEFDh
0x1800137e9  jz      short loc_180013811
0x1800137eb  lea     eax, [r9-300h]
0x1800137f2  cmp     eax, 3
0x1800137f5  jbe     short loc_180013811
0x1800137f7  cmp     ebx, 0FEFFh
0x1800137fd  jz      short loc_180013811
0x1800137ff  mov     ebx, 80090029h
0x180013804  mov     r9d, 0A74h
0x18001380a  mov     ecx, 80090029h
0x18001380f  jmp     short loc_1800137CB
0x180013811  mov     edx, [rsp+68h+arg_20]
0x180013818  mov     ecx, ebx
0x18001381a  call    LookupCipherSuite
0x18001381f  mov     rsi, rax
0x180013822  test    rax, rax
0x180013825  jz      loc_18001390A
0x18001382b  cmp     dword ptr [rax+64h], 1
0x18001382f  jnz     loc_18001390A
0x180013835  cmp     [rsp+68h+arg_28], 0
0x18001383e  jnz     short loc_18001384B
0x180013840  mov     r9d, 0A83h
0x180013846  jmp     loc_1800137C1
0x18001384b  test    [rsp+68h+arg_48], 0FFFFFFFEh
0x180013856  jz      short loc_18001386D
0x180013858  mov     ebx, 80090009h
0x18001385d  mov     r9d, 0A8Ah
0x180013863  mov     ecx, 80090009h
0x180013868  jmp     loc_1800137CB
0x18001386d  mov     ecx, 3Ch ; '<'
0x180013872  call    SafeAllocaAllocateFromHeap
0x180013877  mov     rdi, rax
0x18001387a  test    rax, rax
0x18001387d  jnz     short loc_180013894
0x18001387f  mov     ebx, 8009000Eh
0x180013884  mov     ecx, 8009000Eh
0x180013889  mov     r9d, 0A95h
0x18001388f  jmp     loc_18001391C
0x180013894  mov     rax, [rsp+68h+arg_40]
0x18001389c  xorps   xmm0, xmm0
0x18001389f  mov     r9, [rsp+68h+arg_28]
0x1800138a7  mov     r8, r15
0x1800138aa  movups  xmmword ptr [rdi], xmm0
0x1800138ad  mov     [rsp+68h+var_30], rax
0x1800138b2  mov     rdx, rdi
0x1800138b5  mov     eax, [rsp+68h+arg_38]
0x1800138bc  movups  xmmword ptr [rdi+10h], xmm0
0x1800138c0  mov     [rsp+68h+var_38], eax
0x1800138c4  mov     rax, [rsp+68h+arg_30]
0x1800138cc  movups  xmmword ptr [rdi+20h], xmm0
0x1800138d0  mov     [rsp+68h+var_40], rax
0x1800138d5  movups  xmmword ptr [rdi+2Ch], xmm0
0x1800138d9  mov     dword ptr [rdi], 3Ch ; '<'
0x1800138df  mov     dword ptr [rdi+4], 73736C37h
0x1800138e6  mov     [rdi+8], ebx
0x1800138e9  mov     eax, [rsi+70h]
0x1800138ec  mov     [rsp+68h+var_48], eax
0x1800138f0  call    TlsEncryptPreMasterKey
0x1800138f5  mov     ebx, eax
0x1800138f7  test    eax, eax
0x1800138f9  jns     short loc_180013905
0x1800138fb  mov     ecx, eax
0x1800138fd  mov     r9d, 0AA9h
0x180013903  jmp     short loc_18001391C
0x180013905  mov     [r14], rdi
0x180013908  jmp     short loc_18001393C
0x18001390a  xor     edi, edi
0x18001390c  mov     ebx, 80090029h
0x180013911  mov     ecx, 80090029h
0x180013916  mov     r9d, 0A7Ch
0x18001391c  lea     rdx, aStatus; "Status"
0x180013923  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001392a  call    DebugTraceError
0x18001392f  test    rdi, rdi
0x180013932  jz      short loc_18001393C
0x180013934  mov     rcx, rdi
0x180013937  call    MSCryptFree
0x18001393c  mov     eax, ebx
0x18001393e  add     rsp, 40h
0x180013942  pop     r15
0x180013944  pop     r14
0x180013946  pop     rdi
0x180013947  pop     rsi
0x180013948  pop     rbx
0x180013949  retn
```
