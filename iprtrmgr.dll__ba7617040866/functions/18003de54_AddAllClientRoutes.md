# AddAllClientRoutes

- ea: `0x18003de54`
- end: `0x18003e073`
- name: `AddAllClientRoutes`
- size: `543`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180024d28`

## callees

- `0x180011790`
- `0x18003de54`
- `0x18003f1a4`
- `0x180058570`

## import_xrefs

- `iprtprio!ComputeRouteMetric` at `0x18003df71`
- `iprtprio!ComputeRouteMetric` at `0x18003dfd4`
- `iprtprio!ComputeRouteMetric` at `0x18003df71`
- `iprtprio!ComputeRouteMetric` at `0x18003dfd4`

## pseudocode

```c
__int64 __fastcall AddAllClientRoutes(__int64 a1, int a2)
{
  int v2; // r14d
  __int64 result; // rax
  __int128 *v6; // r9
  _DWORD *v7; // rdx
  __int64 v8; // rsi
  __int64 v9; // r8
  __int64 v10; // rbp
  __int64 v11; // rbx
  int *v12; // r8
  __int64 v13; // rbx
  __int128 v14; // [rsp+58h] [rbp-70h] BYREF
  int v15; // [rsp+68h] [rbp-60h] BYREF
  __int128 v16; // [rsp+6Ch] [rbp-5Ch]
  __int128 v17; // [rsp+7Ch] [rbp-4Ch]
  int v18; // [rsp+8Ch] [rbp-3Ch]

  v2 = *(_DWORD *)(a1 + 516);
  result = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v14 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v15) = 0;
    v6 = &v14;
    if ( a1 != -688 )
      LODWORD(v6) = a1 + 688;
    result = McTemplateU0zjzz_EventWriteTransfer(
               (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
               (unsigned int)RasRtrmgrParamTraceInfo,
               (unsigned int)L"Entered: AddAllClientRoutes",
               (_DWORD)v6,
               *(_QWORD *)(a1 + 72),
               (__int64)&v15);
  }
  v7 = *(_DWORD **)(a1 + 504);
  if ( v7 && *(_QWORD *)(a1 + 712) && *v7 )
  {
    v8 = 0;
    while ( 1 )
    {
      v9 = *(_QWORD *)(a1 + 712);
      if ( v2 )
        break;
      if ( *(_DWORD *)(v9 + 24) )
      {
        v10 = 72 * v8;
        *(_OWORD *)&v7[(unsigned __int64)v10 / 4 + 6] = *(_OWORD *)(v9 + 4);
        *(_DWORD *)(*(_QWORD *)(a1 + 504) + v10 + 60) = 10007;
        v13 = *(_QWORD *)(a1 + 504);
        *(_DWORD *)(v13 + v10 + 64) = ComputeRouteMetric(2);
        *(_DWORD *)(*(_QWORD *)(a1 + 504) + v10 + 68) = 1;
        v12 = *(int **)(a1 + 712);
        goto LABEL_13;
      }
LABEL_14:
      v7 = *(_DWORD **)(a1 + 504);
      v8 = (unsigned int)(v8 + 1);
      if ( (unsigned int)v8 >= *v7 )
        return result;
    }
    v10 = 72 * v8;
    v7[(unsigned __int64)v10 / 4 + 4] = *(_DWORD *)v9;
    *(_DWORD *)(*(_QWORD *)(a1 + 504) + v10 + 60) = 10007;
    *(_DWORD *)(*(_QWORD *)(a1 + 504) + v10 + 32) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 504) + v10 + 36) = 0;
    v11 = *(_QWORD *)(a1 + 504);
    *(_DWORD *)(v11 + v10 + 64) = ComputeRouteMetric(2);
    *(_DWORD *)(*(_QWORD *)(a1 + 504) + v10 + 68) = 3;
    v12 = (int *)(*(_QWORD *)(a1 + 712) + 4LL);
LABEL_13:
    result = AddSingleRoute(a2, v10 + *(_QWORD *)(a1 + 504) + 4, *v12, 0, 1, 1, 0, v2, (struct _GUID *)(a1 + 688), 0);
    goto LABEL_14;
  }
  return result;
}

```

## disassembly

```asm
0x18003de54  mov     r11, rsp
0x18003de57  mov     [r11+18h], rbx
0x18003de5b  push    rbp
0x18003de5c  push    rsi
0x18003de5d  push    rdi
0x18003de5e  push    r14
0x18003de60  push    r15
0x18003de62  sub     rsp, 0A0h
0x18003de69  mov     rax, cs:__security_cookie
0x18003de70  xor     rax, rsp
0x18003de73  mov     [rsp+0C8h+var_38], rax
0x18003de7b  mov     r14d, [rcx+204h]
0x18003de82  xor     eax, eax
0x18003de84  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18003de8b  xorps   xmm0, xmm0
0x18003de8e  mov     [rsp+0C8h+var_60], eax
0x18003de92  mov     r15d, edx
0x18003de95  movups  [rsp+0C8h+var_5C], xmm0
0x18003de9a  mov     rdi, rcx
0x18003de9d  movups  [rsp+0C8h+var_4C], xmm0
0x18003dea2  mov     [r11-3Ch], eax
0x18003dea6  movups  [rsp+0C8h+var_70], xmm0
0x18003deab  jz      short loc_18003DEF0
0x18003dead  mov     word ptr [rsp+0C8h+var_60], ax
0x18003deb2  lea     r9, [r11-70h]
0x18003deb6  lea     rax, [rcx+2B0h]
0x18003debd  test    rax, rax
0x18003dec0  lea     r8, aEnteredAddallc; "Entered: AddAllClientRoutes"
0x18003dec7  lea     rdx, RasRtrmgrParamTraceInfo
0x18003dece  cmovnz  r9, rax
0x18003ded2  lea     rax, [r11-60h]
0x18003ded6  mov     qword ptr [rsp+0C8h+var_A0], rax
0x18003dedb  mov     rax, [rcx+48h]
0x18003dedf  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003dee6  mov     qword ptr [rsp+0C8h+var_A8], rax
0x18003deeb  call    McTemplateU0zjzz_EventWriteTransfer
0x18003def0  mov     rdx, [rdi+1F8h]
0x18003def7  test    rdx, rdx
0x18003defa  jz      loc_18003E04C
0x18003df00  cmp     qword ptr [rdi+2C8h], 0
0x18003df08  jz      loc_18003E04C
0x18003df0e  cmp     dword ptr [rdx], 0
0x18003df11  jbe     loc_18003E04C
0x18003df17  xor     esi, esi
0x18003df19  mov     r8, [rdi+2C8h]
0x18003df20  test    r14d, r14d
0x18003df23  jz      short loc_18003DF97
0x18003df25  mov     eax, [r8]
0x18003df28  lea     rcx, [rsi+rsi*8]
0x18003df2c  lea     rbp, ds:0[rcx*8]
0x18003df34  mov     ecx, 2
0x18003df39  mov     [rdx+rbp+10h], eax
0x18003df3d  mov     rax, [rdi+1F8h]
0x18003df44  mov     dword ptr [rax+rbp+3Ch], 2717h
0x18003df4c  mov     rax, [rdi+1F8h]
0x18003df53  mov     dword ptr [rax+rbp+20h], 0
0x18003df5b  mov     rax, [rdi+1F8h]
0x18003df62  mov     dword ptr [rax+rbp+24h], 0
0x18003df6a  mov     rbx, [rdi+1F8h]
0x18003df71  call    cs:__imp_ComputeRouteMetric
0x18003df77  mov     [rbx+rbp+40h], eax
0x18003df7b  mov     rax, [rdi+1F8h]
0x18003df82  mov     dword ptr [rax+rbp+44h], 3
0x18003df8a  mov     r8, [rdi+2C8h]
0x18003df91  add     r8, 4
0x18003df95  jmp     short loc_18003DFF4
0x18003df97  cmp     dword ptr [r8+18h], 0
0x18003df9c  jz      loc_18003E03B
0x18003dfa2  movups  xmm0, xmmword ptr [r8+4]
0x18003dfa7  lea     rcx, [rsi+rsi*8]
0x18003dfab  lea     rbp, ds:0[rcx*8]
0x18003dfb3  mov     ecx, 2
0x18003dfb8  movdqu  xmmword ptr [rdx+rbp+18h], xmm0
0x18003dfbe  mov     rax, [rdi+1F8h]
0x18003dfc5  mov     dword ptr [rax+rbp+3Ch], 2717h
0x18003dfcd  mov     rbx, [rdi+1F8h]
0x18003dfd4  call    cs:__imp_ComputeRouteMetric
0x18003dfda  mov     [rbx+rbp+40h], eax
0x18003dfde  mov     rax, [rdi+1F8h]
0x18003dfe5  mov     dword ptr [rax+rbp+44h], 1
0x18003dfed  mov     r8, [rdi+2C8h]
0x18003dff4  mov     rdx, [rdi+1F8h]
0x18003dffb  lea     rcx, [rdi+2B0h]
0x18003e002  mov     r8d, [r8]; int
0x18003e005  xor     r9d, r9d; int
0x18003e008  mov     [rsp+0C8h+var_80], r9; __int64
0x18003e00d  add     rdx, 4
0x18003e011  mov     [rsp+0C8h+var_88], rcx; struct _GUID *
0x18003e016  add     rdx, rbp; int
0x18003e019  mov     [rsp+0C8h+var_90], r14d; int
0x18003e01e  mov     ecx, r15d; int
0x18003e021  mov     [rsp+0C8h+var_98], r9d; int
0x18003e026  mov     [rsp+0C8h+var_A0], 1; int
0x18003e02e  mov     [rsp+0C8h+var_A8], 1; int
0x18003e036  call    AddSingleRoute
0x18003e03b  mov     rdx, [rdi+1F8h]
0x18003e042  inc     esi
0x18003e044  cmp     esi, [rdx]
0x18003e046  jb      loc_18003DF19
0x18003e04c  mov     rcx, [rsp+0C8h+var_38]
0x18003e054  xor     rcx, rsp; StackCookie
0x18003e057  call    __security_check_cookie
0x18003e05c  mov     rbx, [rsp+0C8h+arg_10]
0x18003e064  add     rsp, 0A0h
0x18003e06b  pop     r15
0x18003e06d  pop     r14
0x18003e06f  pop     rdi
0x18003e070  pop     rsi
0x18003e071  pop     rbp
0x18003e072  retn
```
