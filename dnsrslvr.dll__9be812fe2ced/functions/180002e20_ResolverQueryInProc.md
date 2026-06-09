# ResolverQueryInProc

- ea: `0x180002e20`
- end: `0x180003237`
- name: `ResolverQueryInProc`
- size: `1047`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, int, int, int, __int64, __int16, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180002d60`
- `0x180002e20`
- `0x180003240`
- `0x1800040a0`
- `0x1800226e0`
- `0x180046ec0`
- `0x18005020c`
- `0x180078ad8`
- `0x18007d860`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `DNSAPI!AddRefQueryBlobEx` at `0x180002f1b`
- `DNSAPI!AddRefQueryBlobEx` at `0x180002f1b`
- `DNSAPI!DeRefQueryBlobEx` at `0x180003018`
- `DNSAPI!DeRefQueryBlobEx` at `0x180003032`
- `DNSAPI!DeRefQueryBlobEx` at `0x180003018`
- `DNSAPI!DeRefQueryBlobEx` at `0x180003032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030d7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800030c5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800030c5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003084`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003084`

## pseudocode

```c
__int64 __fastcall ResolverQueryInProc(
        void *Src,
        unsigned __int16 a2,
        unsigned int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        __int64 a8,
        __int16 a9,
        _QWORD *a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15)
{
  _QWORD *v15; // r11
  int v16; // r10d
  DWORD v18; // eax
  DWORD LastError; // ebx
  __int64 v20; // r8
  HANDLE EventW; // rsi
  __int64 v22; // rbx
  __int64 v23; // rcx
  bool v24; // zf
  __int64 v25; // rcx
  __int64 v27; // rdx
  __int64 v31; // [rsp+B8h] [rbp-19h] BYREF

  v15 = a10;
  v16 = a4;
  v31 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    WPP_SF_SDDlDDDqHqqdqq(
      (_DWORD)Src,
      a13,
      a2,
      (_DWORD)Src,
      a2,
      a3,
      a4,
      a5,
      a6,
      a7,
      a8,
      a9,
      (__int64)a10,
      a11,
      *(_DWORD *)a12,
      a13,
      a14);
    v16 = a4;
    v15 = a10;
  }
  v18 = Query_PrepareBlob((__int64)Src, a2, a3, v16, a5, a6, a7, a8, a9, v15, &v31);
  LastError = v18;
  if ( v18 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_20;
    v27 = 73;
LABEL_36:
    WPP_SF_d(1035, v27, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v18);
LABEL_20:
    if ( LastError != 9506 )
      goto LABEL_13;
    goto LABEL_21;
  }
  AddRefQueryBlobEx(v31, "ResolverQueryInProc", 2245, 2);
  v20 = *(_QWORD *)(a12 + 8);
  if ( *(_DWORD *)a12 || v20 )
  {
    EventW = 0;
    Query_InProcPrepare(v31, a11, v20);
  }
  else
  {
    EventW = CreateEventW(0, 1, 0, 0);
    if ( !EventW )
    {
      LastError = GetLastError();
      goto LABEL_20;
    }
  }
  if ( Src )
  {
    v22 = v31;
    *(_QWORD *)(v22 + 224) = Dns_CreateStringCopy_W(Src);
    v23 = *(_QWORD *)(v31 + 224);
    if ( !v23 )
    {
      LastError = 14;
      goto LABEL_13;
    }
    *(_QWORD *)(v31 + 232) = v23;
    *(_QWORD *)(v31 + 240) = *(_QWORD *)(v31 + 224);
  }
  v24 = g_fHvsiActive == 0;
  *(_OWORD *)(v31 + 272) = *(_OWORD *)a12;
  *(_QWORD *)(v31 + 288) = a13;
  *(_QWORD *)(v31 + 296) = a14;
  *(_QWORD *)(v31 + 1168) = EventW;
  *(_QWORD *)(v31 + 368) = a14 + 16;
  *(_QWORD *)(v31 + 1136) = a15;
  v25 = v31;
  if ( !v24 && (*(_QWORD *)(v31 + 264) & 0x18000000000000LL) == 0x8000000000000LL )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      WPP_SF_(1035, 74, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids);
      v25 = v31;
    }
    v18 = HvsiR_ResolverQuery((_DWORD)Src, a2, a3, a4, a5, (__int64)a10, a14 + 16, v25 + 3384);
    LastError = v18;
    if ( !v18 )
    {
      ResolverCompleteHvsiQuery(v31);
      goto LABEL_12;
    }
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_20;
    v27 = 75;
    goto LABEL_36;
  }
  LastError = ResolverQuery(v31);
  if ( LastError != 9506 )
  {
LABEL_12:
    *(_DWORD *)(a14 + 4) = LastError;
LABEL_13:
    DeRefQueryBlobEx(v31, "ResolverQueryInProc", 2320, 2);
    goto LABEL_14;
  }
  if ( !*(_DWORD *)(v31 + 272) && !*(_QWORD *)(v31 + 280) )
  {
    WaitForSingleObject(EventW, 0xFFFFFFFF);
    LastError = *(_DWORD *)(v31 + 508);
    goto LABEL_20;
  }
LABEL_21:
  if ( !*(_DWORD *)a12 && !*(_QWORD *)(a12 + 8) )
    goto LABEL_13;
LABEL_14:
  DeRefQueryBlobEx(v31, "ResolverQueryInProc", 2323, 0);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 76, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180002e20  push    rbp
0x180002e22  push    rbx
0x180002e23  push    rsi
0x180002e24  push    rdi
0x180002e25  push    r12
0x180002e27  push    r13
0x180002e29  push    r14
0x180002e2b  push    r15
0x180002e2d  lea     rbp, [rsp-7]
0x180002e32  sub     rsp, 0D8h
0x180002e39  mov     rax, cs:__security_cookie
0x180002e40  xor     rax, rsp
0x180002e43  mov     [rbp+3Fh+var_50], rax
0x180002e47  mov     r11, [rbp+3Fh+arg_48]
0x180002e4e  mov     r10d, r9d
0x180002e51  mov     rax, [rbp+3Fh+arg_68]
0x180002e58  mov     r14, rcx
0x180002e5b  mov     rdi, [rbp+3Fh+arg_58]
0x180002e62  mov     rsi, [rbp+3Fh+arg_38]
0x180002e69  mov     r13, [rbp+3Fh+arg_50]
0x180002e70  mov     [rbp+3Fh+var_7C], r9d
0x180002e74  mov     r9d, r8d
0x180002e77  mov     [rbp+3Fh+var_78], r8d
0x180002e7b  movzx   r8d, dx
0x180002e7f  mov     rdx, [rbp+3Fh+arg_60]
0x180002e86  mov     [rbp+3Fh+var_68], rdx
0x180002e8a  mov     [rbp+3Fh+var_80], r8w
0x180002e8f  mov     [rbp+3Fh+var_70], r11
0x180002e93  mov     [rbp+3Fh+var_60], rax
0x180002e97  mov     [rbp+3Fh+var_58], 0
0x180002e9f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180002ea6  movzx   ebx, [rbp+3Fh+arg_40]
0x180002ead  mov     r15d, [rbp+3Fh+arg_30]
0x180002eb1  mov     r12d, [rbp+3Fh+arg_28]
0x180002eb5  jnz     loc_1800030EB
0x180002ebb  mov     r8d, [rbp+3Fh+var_78]
0x180002ebf  lea     rax, [rbp+3Fh+var_58]
0x180002ec3  mov     [rsp+110h+var_C0], rax
0x180002ec8  mov     r9d, r10d
0x180002ecb  mov     eax, [rbp+3Fh+arg_20]
0x180002ece  mov     rcx, r14
0x180002ed1  mov     [rsp+110h+var_C8], r11
0x180002ed6  mov     word ptr [rsp+110h+var_D0], bx
0x180002edb  mov     [rsp+110h+var_D8], rsi
0x180002ee0  mov     dword ptr [rsp+110h+var_E0], r15d
0x180002ee5  mov     dword ptr [rsp+110h+var_E8], r12d
0x180002eea  movzx   r12d, [rbp+3Fh+var_80]
0x180002eef  movzx   edx, r12w
0x180002ef3  mov     [rsp+110h+var_F0], eax
0x180002ef7  call    Query_PrepareBlob
0x180002efc  mov     ebx, eax
0x180002efe  test    eax, eax
0x180002f00  jnz     loc_1800031EE
0x180002f06  mov     rcx, [rbp+3Fh+var_58]
0x180002f0a  lea     r9d, [rax+2]
0x180002f0e  mov     r8d, 8C5h
0x180002f14  lea     rdx, aResolverqueryi; "ResolverQueryInProc"
0x180002f1b  call    cs:__imp_AddRefQueryBlobEx
0x180002f21  mov     r8, [rdi+8]
0x180002f25  cmp     [rdi], ebx
0x180002f27  jnz     short loc_180002F32
0x180002f29  test    r8, r8
0x180002f2c  jz      loc_1800030B9
0x180002f32  mov     rcx, [rbp+3Fh+var_58]
0x180002f36  xor     esi, esi
0x180002f38  mov     rdx, r13
0x180002f3b  call    Query_InProcPrepare
0x180002f40  test    r14, r14
0x180002f43  jz      short loc_180002F85
0x180002f45  mov     rbx, [rbp+3Fh+var_58]
0x180002f49  mov     rcx, r14; Src
0x180002f4c  call    Dns_CreateStringCopy_W
0x180002f51  mov     [rbx+0E0h], rax
0x180002f58  mov     rax, [rbp+3Fh+var_58]
0x180002f5c  mov     rcx, [rax+0E0h]
0x180002f63  test    rcx, rcx
0x180002f66  jz      loc_1800030E1
0x180002f6c  mov     [rax+0E8h], rcx
0x180002f73  mov     rcx, [rbp+3Fh+var_58]
0x180002f77  mov     rax, [rcx+0E0h]
0x180002f7e  mov     [rcx+0F0h], rax
0x180002f85  cmp     cs:g_fHvsiActive, 0
0x180002f8c  mov     rax, [rbp+3Fh+var_58]
0x180002f90  mov     rcx, [rbp+3Fh+var_68]
0x180002f94  mov     r15, [rbp+3Fh+var_60]
0x180002f98  movups  xmm0, xmmword ptr [rdi]
0x180002f9b  movdqu  xmmword ptr [rax+110h], xmm0
0x180002fa3  mov     rax, [rbp+3Fh+var_58]
0x180002fa7  lea     rbx, [r15+10h]
0x180002fab  mov     [rax+120h], rcx
0x180002fb2  mov     rax, [rbp+3Fh+var_58]
0x180002fb6  mov     rcx, [rbp+3Fh+arg_70]
0x180002fbd  mov     [rax+128h], r15
0x180002fc4  mov     rax, [rbp+3Fh+var_58]
0x180002fc8  mov     [rax+490h], rsi
0x180002fcf  mov     rax, [rbp+3Fh+var_58]
0x180002fd3  mov     [rax+170h], rbx
0x180002fda  mov     rax, [rbp+3Fh+var_58]
0x180002fde  mov     [rax+470h], rcx
0x180002fe5  mov     rcx, [rbp+3Fh+var_58]
0x180002fe9  jnz     loc_180003147
0x180002fef  call    ResolverQuery
0x180002ff4  mov     ebx, eax
0x180002ff6  cmp     eax, 2522h
0x180002ffb  jz      short loc_180003067
0x180002ffd  mov     [r15+4], ebx
0x180003001  mov     rcx, [rbp+3Fh+var_58]
0x180003005  lea     rdx, aResolverqueryi; "ResolverQueryInProc"
0x18000300c  mov     r9d, 2
0x180003012  mov     r8d, 910h
0x180003018  call    cs:__imp_DeRefQueryBlobEx
0x18000301e  mov     rcx, [rbp+3Fh+var_58]
0x180003022  lea     rdx, aResolverqueryi; "ResolverQueryInProc"
0x180003029  xor     r9d, r9d
0x18000302c  mov     r8d, 913h
0x180003032  call    cs:__imp_DeRefQueryBlobEx
0x180003038  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18000303f  jnz     loc_180003219
0x180003045  mov     eax, ebx
0x180003047  mov     rcx, [rbp+3Fh+var_50]
0x18000304b  xor     rcx, rsp; StackCookie
0x18000304e  call    __security_check_cookie
0x180003053  add     rsp, 0D8h
0x18000305a  pop     r15
0x18000305c  pop     r14
0x18000305e  pop     r13
0x180003060  pop     r12
0x180003062  pop     rdi
0x180003063  pop     rsi
0x180003064  pop     rbx
0x180003065  pop     rbp
0x180003066  retn
0x180003067  mov     rax, [rbp+3Fh+var_58]
0x18000306b  cmp     dword ptr [rax+110h], 0
0x180003072  jnz     short loc_1800030A0
0x180003074  cmp     qword ptr [rax+118h], 0
0x18000307c  jnz     short loc_1800030A0
0x18000307e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003081  mov     rcx, rsi; hHandle
0x180003084  call    cs:__imp_WaitForSingleObject
0x18000308a  mov     rax, [rbp+3Fh+var_58]
0x18000308e  mov     ebx, [rax+1FCh]
0x180003094  cmp     ebx, 2522h
0x18000309a  jnz     loc_180003001
0x1800030a0  cmp     dword ptr [rdi], 0
0x1800030a3  jnz     loc_18000301E
0x1800030a9  cmp     qword ptr [rdi+8], 0
0x1800030ae  jnz     loc_18000301E
0x1800030b4  jmp     loc_180003001
0x1800030b9  xor     r9d, r9d; lpName
0x1800030bc  xor     r8d, r8d; bInitialState
0x1800030bf  xor     ecx, ecx; lpEventAttributes
0x1800030c1  lea     edx, [r9+1]; bManualReset
0x1800030c5  call    cs:__imp_CreateEventW
0x1800030cb  mov     rsi, rax
0x1800030ce  test    rax, rax
0x1800030d1  jnz     loc_180002F40
0x1800030d7  call    cs:__imp_GetLastError
0x1800030dd  mov     ebx, eax
0x1800030df  jmp     short loc_180003094
0x1800030e1  mov     ebx, 0Eh
0x1800030e6  jmp     loc_180003001
0x1800030eb  mov     [rsp+110h+var_90], rax
0x1800030f3  mov     eax, [rdi]
0x1800030f5  mov     [rsp+110h+var_98], rdx
0x1800030fa  mov     [rsp+110h+var_A0], eax
0x1800030fe  mov     eax, [rbp+3Fh+arg_20]
0x180003101  mov     [rsp+110h+var_A8], r13
0x180003106  mov     [rsp+110h+var_B0], r11
0x18000310b  mov     [rsp+110h+var_B8], bx
0x180003110  mov     [rsp+110h+var_C0], rsi
0x180003115  mov     dword ptr [rsp+110h+var_C8], r15d
0x18000311a  mov     [rsp+110h+var_D0], r12d
0x18000311f  mov     dword ptr [rsp+110h+var_D8], eax
0x180003123  mov     dword ptr [rsp+110h+var_E0], r10d
0x180003128  mov     dword ptr [rsp+110h+var_E8], r9d
0x18000312d  mov     r9, r14
0x180003130  mov     [rsp+110h+var_F0], r8d
0x180003135  call    WPP_SF_SDDlDDDqHqqdqq
0x18000313a  mov     r10d, [rbp+3Fh+var_7C]
0x18000313e  mov     r11, [rbp+3Fh+var_70]
0x180003142  jmp     loc_180002EBB
0x180003147  mov     rax, [rcx+108h]
0x18000314e  mov     rdx, 18000000000000h
0x180003158  and     rax, rdx
0x18000315b  mov     rdx, 8000000000000h
0x180003165  cmp     rax, rdx
0x180003168  jnz     loc_180002FEF
0x18000316e  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180003175  jz      short loc_180003191
0x180003177  mov     edx, 4Ah ; 'J'
0x18000317c  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180003183  mov     ecx, 40Bh
0x180003188  call    WPP_SF_
0x18000318d  mov     rcx, [rbp+3Fh+var_58]
0x180003191  mov     r9d, [rbp+3Fh+var_7C]
0x180003195  lea     rax, [rcx+0D38h]
0x18000319c  mov     r8d, [rbp+3Fh+var_78]
0x1800031a0  movzx   edx, r12w
0x1800031a4  mov     [rsp+110h+var_D8], rax
0x1800031a9  mov     rcx, r14
0x1800031ac  mov     rax, [rbp+3Fh+var_70]
0x1800031b0  mov     [rsp+110h+var_E0], rbx
0x1800031b5  mov     [rsp+110h+var_E8], rax
0x1800031ba  mov     eax, [rbp+3Fh+arg_20]
0x1800031bd  mov     [rsp+110h+var_F0], eax
0x1800031c1  call    HvsiR_ResolverQuery
0x1800031c6  mov     ebx, eax
0x1800031c8  test    eax, eax
0x1800031ca  jnz     short loc_1800031DA
0x1800031cc  mov     rcx, [rbp+3Fh+var_58]
0x1800031d0  call    ResolverCompleteHvsiQuery
0x1800031d5  jmp     loc_180002FFD
0x1800031da  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800031e1  jz      loc_180003094
0x1800031e7  mov     edx, 4Bh ; 'K'
0x1800031ec  jmp     short loc_180003200
0x1800031ee  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800031f5  jz      loc_180003094
0x1800031fb  mov     edx, 49h ; 'I'
0x180003200  mov     r9d, eax
0x180003203  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x18000320a  mov     ecx, 40Bh
0x18000320f  call    WPP_SF_d
0x180003214  jmp     loc_180003094
0x180003219  mov     edx, 4Ch ; 'L'
0x18000321e  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180003225  mov     ecx, 40Bh
0x18000322a  mov     r9d, ebx
0x18000322d  call    WPP_SF_d
0x180003232  jmp     loc_180003045
```
