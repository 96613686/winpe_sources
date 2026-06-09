# MQADsPathToFormatName

- ea: `0x18000e200`
- end: `0x18000e51a`
- name: `MQADsPathToFormatName`
- size: `794`
- prototype: `HRESULT __stdcall(LPCWSTR lpwcsADsPath, LPWSTR lpwcsFormatName, LPDWORD lpdwFormatNameLength)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops`

## callees

- `0x1800027f4`
- `0x180005488`
- `0x180009254`
- `0x18000e200`
- `0x180013bdc`
- `0x180013c74`
- `0x180014458`
- `0x180017ce0`
- `0x180017edc`
- `0x18001d560`
- `0x180021060`
- `0x1800216a8`
- `0x180023c36`
- `0x180026010`

## pseudocode

```c
HRESULT __stdcall MQADsPathToFormatName(LPCWSTR lpwcsADsPath, LPWSTR lpwcsFormatName, LPDWORD lpdwFormatNameLength)
{
  int v6; // eax
  bool v7; // dl
  void (*v8)(void); // rcx
  bool v9; // r8
  bool v10; // r9
  HRESULT v11; // ebx
  wchar_t *v13; // rsi
  int v14; // ebx
  int v15; // eax
  wchar_t *v16; // rcx
  __int128 v17; // xmm6
  int v18; // ebx
  int v19; // edi
  __int64 v20; // [rsp+0h] [rbp-108h] BYREF
  int v21; // [rsp+30h] [rbp-D8h]
  int v22; // [rsp+34h] [rbp-D4h]
  unsigned int v23; // [rsp+38h] [rbp-D0h]
  HRESULT v24; // [rsp+40h] [rbp-C8h]
  HRESULT v25; // [rsp+44h] [rbp-C4h]
  HRESULT v26; // [rsp+48h] [rbp-C0h]
  wchar_t *v27; // [rsp+50h] [rbp-B8h] BYREF
  wchar_t *v28; // [rsp+58h] [rbp-B0h]
  __int64 *v29; // [rsp+60h] [rbp-A8h]
  _OWORD v30[2]; // [rsp+68h] [rbp-A0h] BYREF
  wchar_t *v31[2]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v32; // [rsp+98h] [rbp-70h]
  __int128 v33; // [rsp+A0h] [rbp-68h]
  wchar_t *DomainNameFromDLPath; // [rsp+B0h] [rbp-58h]
  int v35; // [rsp+128h] [rbp+20h] BYREF

  v29 = &v20;
  v6 = RtpOneTimeThreadInit();
  v11 = v6;
  if ( v6 < 0 )
  {
    LogMsgHR(v6, (wchar_t *)L"rt/queue", 0x480u);
    return v11;
  }
  v23 = 1;
  memset(v30, 0, sizeof(v30));
  v27 = 0;
  v13 = 0;
  v28 = 0;
  *(_OWORD *)v31 = 0;
  v32 = 0;
  v35 = 0;
  LOWORD(v31[0]) = 1;
  v14 = ADInit(v8, v7, v9, v10);
  if ( v14 >= 0 )
    v14 = (*(__int64 (__fastcall **)(__int64, LPCWSTR, wchar_t **, int *))(*(_QWORD *)g_pAD + 264LL))(
            g_pAD,
            lpwcsADsPath,
            v31,
            &v35);
  v15 = RTpConvertToMQCode(v14, 1u);
  v21 = v15;
  v22 = v14;
  if ( v15 < 0 )
  {
    v24 = LogHR(v15, (wchar_t *)L"rt/queue", 0x482u);
    local_unwind_0(v29, &loc_18000E31F);
    return v24;
  }
  if ( !v35 )
  {
    v33 = *(_OWORD *)v31[1];
    v17 = v33;
    DomainNameFromDLPath = RTpExtractDomainNameFromDLPath(lpwcsADsPath);
    LOWORD(v30[0]) = 6;
    *(_OWORD *)((char *)v30 + 8) = v17;
    *((_QWORD *)&v30[1] + 1) = DomainNameFromDLPath;
    v16 = v31[1];
    goto LABEL_18;
  }
  if ( v35 != 1 )
  {
    if ( v35 != 2 )
    {
      LogIllegalPoint((wchar_t *)L"rt/queue", 0x485u);
      goto LABEL_19;
    }
    LOWORD(v30[0]) = 1;
    v16 = v31[1];
    *(_OWORD *)((char *)v30 + 8) = *(_OWORD *)v31[1];
LABEL_18:
    operator delete(v16);
    goto LABEL_19;
  }
  v13 = v31[1];
  v28 = v31[1];
  if ( !(unsigned int)FnFormatNameToQueueFormat(v31[1], (struct QUEUE_FORMAT *)v30, &v27) )
  {
    v25 = LogHR(-1072824290, (wchar_t *)L"rt/queue", 0xEBAu);
    local_unwind_0(v29, &loc_18000E3C4);
    return v25;
  }
  if ( LOBYTE(v30[0]) != 2 && ((LOBYTE(v30[0]) - 1) & 0xFFFFFFFD) != 0 )
  {
    v26 = LogHR(-1072824288, (wchar_t *)L"rt/queue", 0xEBBu);
    local_unwind_0(v29, &loc_18000E411);
    return v26;
  }
LABEL_19:
  v18 = RTpQueueFormatToFormatName(
          (struct QUEUE_FORMAT *)v30,
          lpwcsFormatName,
          *lpdwFormatNameLength,
          lpdwFormatNameLength);
  v19 = RTpConvertToMQCode(v18, 1u);
  v21 = v19;
  v22 = v18;
  MmDeallocate(v27);
  MmDeallocate(v13);
  if ( v19 < 0 )
    LogMsgHR(v19, (wchar_t *)L"rt/queue", 0x21Cu);
  return v19;
}

```

## disassembly

```asm
0x18000e200  mov     rax, rsp
0x18000e203  push    rbx
0x18000e204  push    rsi
0x18000e205  push    rdi
0x18000e206  push    r12
0x18000e208  push    r14
0x18000e20a  push    r15
0x18000e20c  sub     rsp, 0D8h
0x18000e213  movaps  xmmword ptr [rax-48h], xmm6
0x18000e217  mov     [rsp+108h+var_A8], rsp
0x18000e21c  mov     r14, r8
0x18000e21f  mov     r15, rdx
0x18000e222  mov     rdi, rcx
0x18000e225  call    ?RtpOneTimeThreadInit@@YAJXZ; RtpOneTimeThreadInit(void)
0x18000e22a  mov     ebx, eax
0x18000e22c  test    eax, eax
0x18000e22e  jns     short loc_18000E25F
0x18000e230  mov     r8d, 480h; unsigned __int16
0x18000e236  lea     rdx, aRtQueue; "rt/queue"
0x18000e23d  mov     ecx, eax; int
0x18000e23f  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000e244  mov     eax, ebx
0x18000e246  movaps  xmm6, [rsp+108h+var_48]
0x18000e24e  add     rsp, 0D8h
0x18000e255  pop     r15
0x18000e257  pop     r14
0x18000e259  pop     r12
0x18000e25b  pop     rdi
0x18000e25c  pop     rsi
0x18000e25d  pop     rbx
0x18000e25e  retn
0x18000e25f  mov     r12d, 1
0x18000e265  mov     [rsp+108h+var_D0], r12d
0x18000e26a  xorps   xmm0, xmm0
0x18000e26d  movups  [rsp+108h+var_A0], xmm0
0x18000e272  movups  [rsp+108h+var_90], xmm0
0x18000e277  mov     [rsp+108h+var_B8], 0
0x18000e280  xor     esi, esi
0x18000e282  mov     [rsp+108h+var_B0], rsi
0x18000e287  xor     eax, eax
0x18000e289  movups  xmmword ptr [rsp+108h+var_80], xmm0
0x18000e291  mov     [rsp+108h+var_70], rax
0x18000e299  mov     [rsp+108h+arg_18], eax
0x18000e2a0  mov     word ptr [rsp+108h+var_80], r12w
0x18000e2a9  call    ?ADInit@@YAJP6AXXZ_N11@Z; ADInit(void (*)(void),bool,bool,bool)
0x18000e2ae  mov     ebx, eax
0x18000e2b0  test    eax, eax
0x18000e2b2  js      short loc_18000E2DF
0x18000e2b4  mov     rcx, cs:?g_pAD@@3V?$P@VCBaseADProvider@@@@A; P<CBaseADProvider> g_pAD
0x18000e2bb  mov     rax, [rcx]
0x18000e2be  lea     r9, [rsp+108h+arg_18]
0x18000e2c6  lea     r8, [rsp+108h+var_80]
0x18000e2ce  mov     rdx, rdi
0x18000e2d1  mov     rax, [rax+108h]
0x18000e2d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2dd  mov     ebx, eax
0x18000e2df  mov     edx, r12d; unsigned int
0x18000e2e2  mov     ecx, ebx; int
0x18000e2e4  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000e2e9  mov     [rsp+108h+var_D8], eax
0x18000e2ed  mov     [rsp+108h+var_D4], ebx
0x18000e2f1  test    eax, eax
0x18000e2f3  jns     short loc_18000E328
0x18000e2f5  mov     r8d, 482h; unsigned __int16
0x18000e2fb  lea     rdx, aRtQueue; "rt/queue"
0x18000e302  mov     ecx, eax; int
0x18000e304  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x18000e309  mov     [rsp+108h+var_C8], eax
0x18000e30d  lea     rdx, loc_18000E31F
0x18000e314  mov     rcx, [rsp+108h+var_A8]
0x18000e319  call    _local_unwind_0
0x18000e31e  nop
0x18000e31f  mov     eax, [rsp+108h+var_C8]
0x18000e323  jmp     loc_18000E246
0x18000e328  mov     ecx, [rsp+108h+arg_18]
0x18000e32f  test    ecx, ecx
0x18000e331  jz      loc_18000E41A
0x18000e337  sub     ecx, 1
0x18000e33a  jz      short loc_18000E374
0x18000e33c  cmp     ecx, 1
0x18000e33f  jz      short loc_18000E357
0x18000e341  mov     edx, 485h; unsigned __int16
0x18000e346  lea     rcx, aRtQueue; "rt/queue"
0x18000e34d  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x18000e352  jmp     loc_18000E45F
0x18000e357  mov     word ptr [rsp+108h+var_A0], 1
0x18000e35e  mov     rcx, [rsp+108h+var_80+8]
0x18000e366  movups  xmm0, xmmword ptr [rcx]
0x18000e369  movdqu  [rsp+108h+var_A0+8], xmm0
0x18000e36f  jmp     loc_18000E45A
0x18000e374  mov     rsi, [rsp+108h+var_80+8]
0x18000e37c  mov     [rsp+108h+var_B0], rsi
0x18000e381  lea     r8, [rsp+108h+var_B8]; wchar_t **
0x18000e386  lea     rdx, [rsp+108h+var_A0]; struct QUEUE_FORMAT *
0x18000e38b  mov     rcx, rsi; wchar_t *
0x18000e38e  call    ?FnFormatNameToQueueFormat@@YAHPEB_WPEAUQUEUE_FORMAT@@PEAPEA_W@Z; FnFormatNameToQueueFormat(wchar_t const *,QUEUE_FORMAT *,wchar_t * *)
0x18000e393  test    eax, eax
0x18000e395  jnz     short loc_18000E3CD
0x18000e397  mov     r8d, 0EBAh; unsigned __int16
0x18000e39d  lea     rdx, aRtQueue; "rt/queue"
0x18000e3a4  mov     ecx, 0C00E001Eh; int
0x18000e3a9  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x18000e3ae  mov     [rsp+108h+var_C4], eax
0x18000e3b2  lea     rdx, loc_18000E3C4
0x18000e3b9  mov     rcx, [rsp+108h+var_A8]
0x18000e3be  call    _local_unwind_0
0x18000e3c3  nop
0x18000e3c4  mov     eax, [rsp+108h+var_C4]
0x18000e3c8  jmp     loc_18000E246
0x18000e3cd  movzx   eax, byte ptr [rsp+108h+var_A0]
0x18000e3d2  cmp     eax, 2
0x18000e3d5  jz      loc_18000E45F
0x18000e3db  dec     eax
0x18000e3dd  test    eax, 0FFFFFFFDh
0x18000e3e2  jz      short loc_18000E45F
0x18000e3e4  mov     r8d, 0EBBh; unsigned __int16
0x18000e3ea  lea     rdx, aRtQueue; "rt/queue"
0x18000e3f1  mov     ecx, 0C00E0020h; int
0x18000e3f6  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x18000e3fb  mov     [rsp+108h+var_C0], eax
0x18000e3ff  lea     rdx, loc_18000E411
0x18000e406  mov     rcx, [rsp+108h+var_A8]
0x18000e40b  call    _local_unwind_0
0x18000e410  nop
0x18000e411  mov     eax, [rsp+108h+var_C0]
0x18000e415  jmp     loc_18000E246
0x18000e41a  mov     rax, [rsp+108h+var_80+8]
0x18000e422  movups  xmm6, xmmword ptr [rax]
0x18000e425  movups  [rsp+108h+var_68], xmm6
0x18000e42d  mov     rcx, rdi; wchar_t *
0x18000e430  call    ?RTpExtractDomainNameFromDLPath@@YAPEA_WPEB_W@Z; RTpExtractDomainNameFromDLPath(wchar_t const *)
0x18000e435  mov     [rsp+108h+var_58], rax
0x18000e43d  mov     word ptr [rsp+108h+var_A0], 6
0x18000e444  movdqu  [rsp+108h+var_A0+8], xmm6
0x18000e44a  mov     qword ptr [rsp+108h+var_90+8], rax
0x18000e452  mov     rcx, [rsp+108h+var_80+8]; void *
0x18000e45a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e45f  mov     r9, r14; unsigned int *
0x18000e462  mov     r8d, [r14]; unsigned int
0x18000e465  mov     rdx, r15; wchar_t *
0x18000e468  lea     rcx, [rsp+108h+var_A0]; struct QUEUE_FORMAT *
0x18000e46d  call    ?RTpQueueFormatToFormatName@@YAJPEAUQUEUE_FORMAT@@PEA_WKPEAK@Z; RTpQueueFormatToFormatName(QUEUE_FORMAT *,wchar_t *,ulong,ulong *)
0x18000e472  mov     ebx, eax
0x18000e474  mov     edx, r12d; unsigned int
0x18000e477  mov     ecx, eax; int
0x18000e479  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000e47e  mov     edi, eax
0x18000e480  mov     [rsp+108h+var_D8], eax
0x18000e484  mov     [rsp+108h+var_D4], ebx
0x18000e488  jmp     short loc_18000E4E9
0x18000e48a  mov     ebx, eax
0x18000e48c  mov     edx, [rsp+108h+var_D0]; unsigned int
0x18000e490  mov     ecx, eax; int
0x18000e492  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000e497  mov     edi, eax
0x18000e499  mov     [rsp+108h+var_D8], eax
0x18000e49d  mov     [rsp+108h+var_D4], ebx
0x18000e4a1  test    eax, eax
0x18000e4a3  jg      short loc_18000E4A9
0x18000e4a5  mov     ecx, eax
0x18000e4a7  jmp     short loc_18000E4B2
0x18000e4a9  movzx   ecx, di
0x18000e4ac  or      ecx, 80070000h; int
0x18000e4b2  mov     r8d, 68Eh; unsigned __int16
0x18000e4b8  lea     rdx, aRtQueue; "rt/queue"
0x18000e4bf  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x18000e4c4  test    edi, edi
0x18000e4c6  js      short loc_18000E4E4
0x18000e4c8  mov     edx, [rsp+108h+var_D0]; unsigned int
0x18000e4cc  mov     ecx, 0C00E000Bh; int
0x18000e4d1  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000e4d6  mov     edi, eax
0x18000e4d8  mov     [rsp+108h+var_D8], eax
0x18000e4dc  mov     [rsp+108h+var_D4], 0C00E000Bh
0x18000e4e4  mov     rsi, [rsp+108h+var_B0]
0x18000e4e9  mov     rcx, [rsp+108h+var_B8]; void *
0x18000e4ee  call    ?MmDeallocate@@YAXPEAX@Z; MmDeallocate(void *)
0x18000e4f3  mov     rcx, rsi; void *
0x18000e4f6  call    ?MmDeallocate@@YAXPEAX@Z; MmDeallocate(void *)
0x18000e4fb  test    edi, edi
0x18000e4fd  jns     short loc_18000E513
0x18000e4ff  mov     r8d, 21Ch; unsigned __int16
0x18000e505  lea     rdx, aRtQueue; "rt/queue"
0x18000e50c  mov     ecx, edi; int
0x18000e50e  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000e513  mov     eax, edi
0x18000e515  jmp     loc_18000E246
0x180024675  push    rbp
0x180024677  sub     rsp, 30h
0x18002467b  mov     rbp, rdx
0x18002467e  mov     rcx, [rbp+50h]; void *
0x180024682  call    ?MmDeallocate@@YAXPEAX@Z; MmDeallocate(void *)
0x180024687  mov     rcx, [rbp+58h]; void *
0x18002468b  call    ?MmDeallocate@@YAXPEAX@Z; MmDeallocate(void *)
0x180024690  nop
0x180024691  add     rsp, 30h
0x180024695  pop     rbp
0x180024696  retn
```
