# MspGetActualCredential(_LUID *,_MSV1_0_PRIMARY_CREDENTIAL *)

- ea: `0x18000dc84`
- end: `0x18000de92`
- name: `?MspGetActualCredential@@YAJPEAU_LUID@@PEAU_MSV1_0_PRIMARY_CREDENTIAL@@@Z`
- size: `526`
- prototype: `__int64 __fastcall(struct _LUID *, struct _MSV1_0_PRIMARY_CREDENTIAL *)`
- caller_count: `4`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000d7c0`
- `0x180025c50`
- `0x1800462b0`
- `0x180046700`

## callees

- `0x18000dc84`
- `0x18000dea0`
- `0x18000df40`
- `0x1800144d4`
- `0x18006d010`

## import_xrefs

- `NtlmShared!MsvpPutClearOwfsInPrimaryCredentialNew` at `0x18000dd60`
- `NtlmShared!MsvpPutClearOwfsInPrimaryCredentialNew` at `0x18000dd60`

## string_xrefs

- `0x18000dd36`: `GetServiceAccountPasswordFailure`

## pseudocode

```c
__int64 __fastcall MspGetActualCredential(struct _LUID *a1, struct _MSV1_0_PRIMARY_CREDENTIAL *a2)
{
  int PrimaryCredential; // eax
  __int64 v4; // rsi
  int v5; // ebx
  _OWORD *v6; // rdi
  int v7; // eax
  const char *v8; // r8
  unsigned int v9; // edx
  __int64 v10; // rcx
  _OWORD *v11; // rax
  __int128 v12; // xmm1
  __int64 v13; // rcx
  _BYTE *v14; // rax
  _BYTE *v15; // rcx
  __int64 v16; // rax
  __int64 v18; // [rsp+40h] [rbp-20h] BYREF
  __int128 v19; // [rsp+48h] [rbp-18h] BYREF
  int v20; // [rsp+90h] [rbp+30h] BYREF
  char v21; // [rsp+98h] [rbp+38h] BYREF

  v18 = 0;
  v20 = 0;
  v19 = 0;
  PrimaryCredential = NlpGetPrimaryCredential(a1, &v18, &v21);
  v4 = v18;
  v5 = PrimaryCredential;
  if ( PrimaryCredential >= 0 )
  {
    v6 = (_OWORD *)(v18 + 32);
    v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *))(**(_QWORD **)(v18 + 32) + 72LL))(
           *(_QWORD *)(v18 + 32),
           v18 + 32,
           &v20);
    if ( v5 >= 0 )
    {
      if ( v20 )
      {
        v7 = ((__int64 (__fastcall *)(__int64, __int64, __int64))qword_1800883D0)(v4 + 16, v4, 1);
        v5 = v7;
        if ( v7 < 0 )
        {
          v8 = "GetServiceAccountPasswordFailure";
          v9 = 94;
LABEL_6:
          NtlmTraceErrorWithStatusViaWpp("MspGetActualCredential", v9, v8, v7);
          goto LABEL_14;
        }
        v7 = MsvpPutClearOwfsInPrimaryCredentialNew(&v19, 0, (char *)a2 + 32);
        v5 = v7;
        if ( v7 < 0 )
        {
          v8 = "MsvpPutClearOwfsInPrimaryCredentialNew";
          v9 = 104;
          goto LABEL_6;
        }
        *((_QWORD *)a2 + 4) = LocalhostNtLmCredIsoObj::IsoObj;
      }
      else
      {
        v10 = 2;
        v11 = (_OWORD *)((char *)a2 + 32);
        do
        {
          *v11 = *v6;
          v11[1] = v6[1];
          v11[2] = v6[2];
          v11[3] = v6[3];
          v11[4] = v6[4];
          v11[5] = v6[5];
          v11[6] = v6[6];
          v12 = v6[7];
          v6 += 8;
          v11[7] = v12;
          v11 += 8;
          --v10;
        }
        while ( v10 );
        *v11 = *v6;
        v11[1] = v6[1];
        v11[2] = v6[2];
        v11[3] = v6[3];
        v11[4] = v6[4];
        v11[5] = v6[5];
      }
      v5 = 0;
    }
  }
LABEL_14:
  if ( v4 )
  {
    v13 = 352;
    v14 = (_BYTE *)(v4 + 32);
    do
    {
      *v14++ = 0;
      --v13;
    }
    while ( v13 );
    ((void (__fastcall *)(__int64))qword_180088240)(v4);
  }
  v15 = (_BYTE *)*((_QWORD *)&v19 + 1);
  if ( *((_QWORD *)&v19 + 1) )
  {
    v16 = (unsigned __int16)v19;
    if ( (_WORD)v19 )
    {
      do
      {
        *v15++ = 0;
        --v16;
      }
      while ( v16 );
    }
    ((void (*)(void))qword_180088240)();
  }
  NtlmTraceStatusViaWpp("MspGetActualCredential", 131, (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000dc84  mov     [rsp-18h+arg_0], rbx
0x18000dc89  mov     [rsp-18h+arg_8], rsi
0x18000dc8e  push    rbp
0x18000dc8f  push    rdi
0x18000dc90  push    r14
0x18000dc92  mov     rbp, rsp
0x18000dc95  sub     rsp, 60h
0x18000dc99  mov     r14, rdx
0x18000dc9c  mov     [rbp+var_20], 0
0x18000dca4  xorps   xmm0, xmm0
0x18000dca7  mov     [rbp+arg_10], 0
0x18000dcae  lea     rdx, [rbp+var_20]
0x18000dcb2  lea     r8, [rbp+arg_18]
0x18000dcb6  movups  [rbp+var_18], xmm0
0x18000dcba  call    NlpGetPrimaryCredential
0x18000dcbf  mov     rsi, [rbp+var_20]
0x18000dcc3  mov     ebx, eax
0x18000dcc5  test    eax, eax
0x18000dcc7  js      loc_18000DE10
0x18000dccd  lea     rdi, [rsi+20h]
0x18000dcd1  mov     rcx, [rdi]
0x18000dcd4  lea     r8, [rbp+arg_10]
0x18000dcd8  mov     rdx, rdi
0x18000dcdb  mov     rax, [rcx]
0x18000dcde  mov     rax, [rax+48h]
0x18000dce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dce7  mov     ebx, eax
0x18000dce9  test    eax, eax
0x18000dceb  js      loc_18000DE10
0x18000dcf1  cmp     [rbp+arg_10], 0
0x18000dcf5  jz      loc_18000DD8A
0x18000dcfb  xor     r9d, r9d
0x18000dcfe  mov     [rsp+60h+var_30], 0
0x18000dd07  lea     rax, [rbp+var_18]
0x18000dd0b  mov     [rsp+60h+var_38], 0
0x18000dd14  mov     [rsp+60h+var_40], rax
0x18000dd19  lea     rcx, [rsi+10h]
0x18000dd1d  mov     rax, cs:qword_1800883D0
0x18000dd24  mov     rdx, rsi
0x18000dd27  lea     r8d, [r9+1]
0x18000dd2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd30  mov     ebx, eax
0x18000dd32  test    eax, eax
0x18000dd34  jns     short loc_18000DD56
0x18000dd36  lea     r8, aGetserviceacco; "GetServiceAccountPasswordFailure"
0x18000dd3d  mov     edx, 5Eh ; '^'; unsigned int
0x18000dd42  mov     r9d, eax; int
0x18000dd45  lea     rcx, aMspgetactualcr; "MspGetActualCredential"
0x18000dd4c  call    ?NtlmTraceErrorWithStatusViaWpp@@YAXPEBDK0J@Z; NtlmTraceErrorWithStatusViaWpp(char const *,ulong,char const *,long)
0x18000dd51  jmp     loc_18000DE10
0x18000dd56  lea     r8, [r14+20h]
0x18000dd5a  xor     edx, edx
0x18000dd5c  lea     rcx, [rbp+var_18]
0x18000dd60  call    cs:__imp_MsvpPutClearOwfsInPrimaryCredentialNew
0x18000dd66  mov     ebx, eax
0x18000dd68  test    eax, eax
0x18000dd6a  jns     short loc_18000DD7A
0x18000dd6c  lea     r8, aMsvpputclearow_0; "MsvpPutClearOwfsInPrimaryCredentialNew"
0x18000dd73  mov     edx, 68h ; 'h'
0x18000dd78  jmp     short loc_18000DD42
0x18000dd7a  mov     rax, cs:?IsoObj@LocalhostNtLmCredIsoObj@@0PEAVNtlmCredIsoApi@@EA; NtlmCredIsoApi * LocalhostNtLmCredIsoObj::IsoObj
0x18000dd81  mov     [r14+20h], rax
0x18000dd85  jmp     loc_18000DE0E
0x18000dd8a  mov     ecx, 2
0x18000dd8f  lea     rax, [r14+20h]
0x18000dd93  lea     edx, [rcx+7Eh]
0x18000dd96  movups  xmm0, xmmword ptr [rdi]
0x18000dd99  movups  xmmword ptr [rax], xmm0
0x18000dd9c  movups  xmm1, xmmword ptr [rdi+10h]
0x18000dda0  movups  xmmword ptr [rax+10h], xmm1
0x18000dda4  movups  xmm0, xmmword ptr [rdi+20h]
0x18000dda8  movups  xmmword ptr [rax+20h], xmm0
0x18000ddac  movups  xmm1, xmmword ptr [rdi+30h]
0x18000ddb0  movups  xmmword ptr [rax+30h], xmm1
0x18000ddb4  movups  xmm0, xmmword ptr [rdi+40h]
0x18000ddb8  movups  xmmword ptr [rax+40h], xmm0
0x18000ddbc  movups  xmm1, xmmword ptr [rdi+50h]
0x18000ddc0  movups  xmmword ptr [rax+50h], xmm1
0x18000ddc4  movups  xmm0, xmmword ptr [rdi+60h]
0x18000ddc8  movups  xmmword ptr [rax+60h], xmm0
0x18000ddcc  movups  xmm1, xmmword ptr [rdi+70h]
0x18000ddd0  add     rdi, rdx
0x18000ddd3  movups  xmmword ptr [rax+70h], xmm1
0x18000ddd7  add     rax, rdx
0x18000ddda  sub     rcx, 1
0x18000ddde  jnz     short loc_18000DD96
0x18000dde0  movups  xmm0, xmmword ptr [rdi]
0x18000dde3  movups  xmmword ptr [rax], xmm0
0x18000dde6  movups  xmm1, xmmword ptr [rdi+10h]
0x18000ddea  movups  xmmword ptr [rax+10h], xmm1
0x18000ddee  movups  xmm0, xmmword ptr [rdi+20h]
0x18000ddf2  movups  xmmword ptr [rax+20h], xmm0
0x18000ddf6  movups  xmm1, xmmword ptr [rdi+30h]
0x18000ddfa  movups  xmmword ptr [rax+30h], xmm1
0x18000ddfe  movups  xmm0, xmmword ptr [rdi+40h]
0x18000de02  movups  xmmword ptr [rax+40h], xmm0
0x18000de06  movups  xmm1, xmmword ptr [rdi+50h]
0x18000de0a  movups  xmmword ptr [rax+50h], xmm1
0x18000de0e  xor     ebx, ebx
0x18000de10  test    rsi, rsi
0x18000de13  jz      short loc_18000DE39
0x18000de15  mov     ecx, 160h
0x18000de1a  lea     rax, [rsi+20h]
0x18000de1e  mov     byte ptr [rax], 0
0x18000de21  inc     rax
0x18000de24  sub     rcx, 1
0x18000de28  jnz     short loc_18000DE1E
0x18000de2a  mov     rax, cs:qword_180088240
0x18000de31  mov     rcx, rsi
0x18000de34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de39  mov     rcx, qword ptr [rbp+var_18+8]
0x18000de3d  test    rcx, rcx
0x18000de40  jz      short loc_18000DE67
0x18000de42  movzx   eax, word ptr [rbp+var_18]
0x18000de46  test    rax, rax
0x18000de49  jz      short loc_18000DE5B
0x18000de4b  mov     byte ptr [rcx], 0
0x18000de4e  inc     rcx
0x18000de51  sub     rax, 1
0x18000de55  jnz     short loc_18000DE4B
0x18000de57  mov     rcx, qword ptr [rbp+var_18+8]
0x18000de5b  mov     rax, cs:qword_180088240
0x18000de62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de67  mov     r8d, ebx
0x18000de6a  lea     rcx, aMspgetactualcr; "MspGetActualCredential"
0x18000de71  mov     edx, 83h
0x18000de76  call    NtlmTraceStatusViaWpp
0x18000de7b  lea     r11, [rsp+60h+var_s0]
0x18000de80  mov     eax, ebx
0x18000de82  mov     rbx, [r11+20h]
0x18000de86  mov     rsi, [r11+28h]
0x18000de8a  mov     rsp, r11
0x18000de8d  pop     r14
0x18000de8f  pop     rdi
0x18000de90  pop     rbp
0x18000de91  retn
```
