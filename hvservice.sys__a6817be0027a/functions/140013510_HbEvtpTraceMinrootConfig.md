# HbEvtpTraceMinrootConfig

- ea: `0x140013510`
- end: `0x1400137aa`
- name: `HbEvtpTraceMinrootConfig`
- size: `666`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000ecd0`
- `0x1400115a0`

## callees

- `0x140001040`
- `0x140001070`
- `0x140002ae0`
- `0x140013510`

## import_xrefs

- `ntoskrnl!ZwQuerySystemInformation` at `0x14001357b`
- `ntoskrnl!ZwQuerySystemInformation` at `0x14001357b`
- `ntoskrnl!ExAllocatePool2` at `0x14001354d`
- `ntoskrnl!ExAllocatePool2` at `0x14001354d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001377f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001377f`

## pseudocode

```c
__int64 HbEvtpTraceMinrootConfig()
{
  unsigned __int16 *Pool2; // rax
  unsigned __int16 *v1; // rbx
  NTSTATUS v2; // edi
  __int64 v3; // r8
  __int64 v4; // r9
  int v5; // ecx
  unsigned int v6; // esi
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rcx
  _WORD v11[2]; // [rsp+30h] [rbp-99h] BYREF
  int v12; // [rsp+34h] [rbp-95h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-91h] BYREF
  int v14; // [rsp+3Ch] [rbp-8Dh] BYREF
  int v15; // [rsp+40h] [rbp-89h] BYREF
  int v16; // [rsp+44h] [rbp-85h] BYREF
  __int64 v17; // [rsp+48h] [rbp-81h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v18[2]; // [rsp+50h] [rbp-79h] BYREF
  int *v19; // [rsp+70h] [rbp-59h]
  __int64 v20; // [rsp+78h] [rbp-51h]
  int *v21; // [rsp+80h] [rbp-49h]
  __int64 v22; // [rsp+88h] [rbp-41h]
  unsigned __int16 *v23; // [rsp+90h] [rbp-39h]
  __int64 v24; // [rsp+98h] [rbp-31h]
  __int64 *v25; // [rsp+A0h] [rbp-29h]
  __int64 v26; // [rsp+A8h] [rbp-21h]
  int *v27; // [rsp+B0h] [rbp-19h]
  __int64 v28; // [rsp+B8h] [rbp-11h]
  int *v29; // [rsp+C0h] [rbp-9h]
  __int64 v30; // [rsp+C8h] [rbp-1h]
  __int64 *v31; // [rsp+D0h] [rbp+7h]
  __int64 v32; // [rsp+D8h] [rbp+Fh]

  ReturnLength = 0;
  Pool2 = (unsigned __int16 *)ExAllocatePool2(258, 17048, 1967284808);
  v1 = Pool2;
  if ( Pool2 )
  {
    v2 = ZwQuerySystemInformation(
           MaxSystemInfoClass|SystemProcessorPerformanceInformation|0x80,
           Pool2,
           0x4298u,
           &ReturnLength);
    if ( v2 >= 0 )
    {
      if ( ReturnLength == 17048 )
      {
        if ( (unsigned int)dword_140009088 > 5 && tlgKeywordOn((__int64)&dword_140009088, 0x400000000002LL) )
        {
          v5 = v1[4];
          v14 = *(_DWORD *)v1;
          v19 = &v14;
          v15 = *((_DWORD *)v1 + 1);
          v21 = &v15;
          v23 = v11;
          v25 = (__int64 *)(v1 + 6);
          v16 = *((_DWORD *)v1 + 35);
          v27 = &v16;
          v12 = *((_DWORD *)v1 + 36);
          v29 = &v12;
          v11[0] = v5;
          v31 = &v17;
          v26 = (unsigned int)(2 * v5);
          v20 = 4;
          v22 = 4;
          v24 = 2;
          v28 = 4;
          v30 = 4;
          v17 = 0x2000000;
          v32 = 8;
          tlgWriteTransfer_EtwWriteTransfer(
            (__int64)&dword_140009088,
            (unsigned __int8 *)&byte_14000736D,
            v3,
            v4,
            9u,
            v18);
        }
        if ( *((_DWORD *)v1 + 37) )
        {
          v6 = 0;
          do
          {
            if ( (unsigned int)dword_140009088 > 5 && tlgKeywordOn((__int64)&dword_140009088, 0x400000000002LL) )
            {
              v9 = 132LL * v6;
              v20 = 4;
              v22 = 2;
              v24 = 256;
              v17 = 0x2000000;
              v12 = *(_DWORD *)&v1[v9 + 76];
              v19 = &v12;
              v11[0] = 32;
              v21 = (int *)v11;
              v26 = 8;
              v23 = &v1[v9 + 80];
              v25 = &v17;
              tlgWriteTransfer_EtwWriteTransfer(
                (__int64)&dword_140009088,
                (unsigned __int8 *)&byte_14000747B,
                v7,
                v8,
                6u,
                v18);
            }
            ++v6;
          }
          while ( v6 < *((_DWORD *)v1 + 37) );
        }
      }
      else
      {
        v2 = -1073741306;
      }
    }
    ExFreePoolWithTag(v1, 0x75426248u);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140013510  push    rbp
0x140013512  push    rbx
0x140013513  push    rsi
0x140013514  push    rdi
0x140013515  push    r13
0x140013517  push    r14
0x140013519  lea     rbp, [rsp-2Fh]
0x14001351e  sub     rsp, 0F8h
0x140013525  mov     rax, cs:__security_cookie
0x14001352c  xor     rax, rsp
0x14001352f  mov     [rbp+57h+var_40], rax
0x140013533  mov     esi, 4298h
0x140013538  xor     r14d, r14d
0x14001353b  mov     edx, esi
0x14001353d  mov     [rsp+120h+ReturnLength], r14d
0x140013542  mov     r8d, 75426248h
0x140013548  mov     ecx, 102h
0x14001354d  call    cs:__imp_ExAllocatePool2
0x140013554  nop     dword ptr [rax+rax+00h]
0x140013559  mov     rbx, rax
0x14001355c  test    rax, rax
0x14001355f  jnz     short loc_14001356B
0x140013561  mov     edi, 0C000009Ah
0x140013566  jmp     loc_14001378B
0x14001356b  lea     r9, [rsp+120h+ReturnLength]; ReturnLength
0x140013570  mov     r8d, esi; SystemInformationLength
0x140013573  mov     rdx, rbx; SystemInformation
0x140013576  mov     ecx, 0EAh; SystemInformationClass
0x14001357b  call    cs:__imp_ZwQuerySystemInformation
0x140013582  nop     dword ptr [rax+rax+00h]
0x140013587  mov     edi, eax
0x140013589  test    eax, eax
0x14001358b  js      loc_140013777
0x140013591  cmp     [rsp+120h+ReturnLength], esi
0x140013595  jz      short loc_1400135A1
0x140013597  mov     edi, 0C0000206h
0x14001359c  jmp     loc_140013777
0x1400135a1  mov     eax, cs:dword_140009088
0x1400135a7  mov     r13, 400000000002h
0x1400135b1  cmp     eax, 5
0x1400135b4  jbe     loc_14001369F
0x1400135ba  mov     rdx, r13
0x1400135bd  lea     rcx, dword_140009088
0x1400135c4  call    _tlgKeywordOn
0x1400135c9  test    al, al
0x1400135cb  jz      loc_14001369F
0x1400135d1  movzx   ecx, word ptr [rbx+8]
0x1400135d5  lea     rdx, byte_14000736D; int
0x1400135dc  mov     eax, [rbx]
0x1400135de  mov     [rsp+120h+var_E4], eax
0x1400135e2  lea     rax, [rsp+120h+var_E4]
0x1400135e7  mov     [rbp+57h+var_B0], rax
0x1400135eb  mov     eax, [rbx+4]
0x1400135ee  mov     [rsp+120h+var_E0], eax
0x1400135f2  lea     rax, [rsp+120h+var_E0]
0x1400135f7  mov     [rbp+57h+var_A0], rax
0x1400135fb  lea     rax, [rsp+120h+var_F0]
0x140013600  mov     [rbp+57h+var_90], rax
0x140013604  lea     rax, [rbx+0Ch]
0x140013608  mov     [rbp+57h+var_80], rax
0x14001360c  mov     eax, [rbx+8Ch]
0x140013612  mov     [rsp+120h+var_DC], eax
0x140013616  lea     rax, [rsp+120h+var_DC]
0x14001361b  mov     [rbp+57h+var_70], rax
0x14001361f  mov     eax, [rbx+90h]
0x140013625  mov     [rsp+120h+var_EC], eax
0x140013629  lea     rax, [rsp+120h+var_EC]
0x14001362e  mov     [rbp+57h+var_60], rax
0x140013632  lea     rax, [rsp+120h+var_D8]
0x140013637  mov     [rsp+120h+var_F0], cx
0x14001363c  add     ecx, ecx
0x14001363e  mov     [rbp+57h+var_50], rax
0x140013642  lea     rax, [rbp+57h+var_D0]
0x140013646  mov     dword ptr [rbp+57h+var_78], ecx
0x140013649  lea     rcx, dword_140009088; int
0x140013650  mov     [rsp+120h+var_F8], rax; __int64
0x140013655  mov     [rsp+120h+var_100], 9; ULONG
0x14001365d  mov     [rbp+57h+var_A8], 4
0x140013665  mov     [rbp+57h+var_98], 4
0x14001366d  mov     [rbp+57h+var_88], 2
0x140013675  mov     dword ptr [rbp+57h+var_78+4], r14d
0x140013679  mov     [rbp+57h+var_68], 4
0x140013681  mov     [rbp+57h+var_58], 4
0x140013689  mov     [rsp+120h+var_D8], 2000000h
0x140013692  mov     [rbp+57h+var_48], 8
0x14001369a  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001369f  cmp     [rbx+94h], r14d
0x1400136a6  jbe     loc_140013777
0x1400136ac  mov     esi, r14d
0x1400136af  mov     eax, cs:dword_140009088
0x1400136b5  cmp     eax, 5
0x1400136b8  jbe     loc_140013769
0x1400136be  mov     rdx, r13
0x1400136c1  lea     rcx, dword_140009088
0x1400136c8  call    _tlgKeywordOn
0x1400136cd  test    al, al
0x1400136cf  jz      loc_140013769
0x1400136d5  mov     eax, esi
0x1400136d7  lea     rdx, byte_14000747B; int
0x1400136de  imul    rcx, rax, 108h
0x1400136e5  mov     [rbp+57h+var_A8], 4
0x1400136ed  mov     [rbp+57h+var_98], 2
0x1400136f5  mov     [rbp+57h+var_88], 100h
0x1400136fd  mov     [rsp+120h+var_D8], 2000000h
0x140013706  mov     eax, [rcx+rbx+98h]
0x14001370d  mov     [rsp+120h+var_EC], eax
0x140013711  lea     rax, [rsp+120h+var_EC]
0x140013716  mov     [rbp+57h+var_B0], rax
0x14001371a  mov     eax, 20h ; ' '
0x14001371f  mov     [rsp+120h+var_F0], ax
0x140013724  lea     rax, [rsp+120h+var_F0]
0x140013729  mov     [rbp+57h+var_A0], rax
0x14001372d  lea     rax, [rbx+0A0h]
0x140013734  add     rax, rcx
0x140013737  mov     [rbp+57h+var_78], 8
0x14001373f  mov     [rbp+57h+var_90], rax
0x140013743  lea     rcx, dword_140009088; int
0x14001374a  lea     rax, [rsp+120h+var_D8]
0x14001374f  mov     [rbp+57h+var_80], rax
0x140013753  lea     rax, [rbp+57h+var_D0]
0x140013757  mov     [rsp+120h+var_F8], rax; __int64
0x14001375c  mov     [rsp+120h+var_100], 6; ULONG
0x140013764  call    _tlgWriteTransfer_EtwWriteTransfer
0x140013769  inc     esi
0x14001376b  cmp     esi, [rbx+94h]
0x140013771  jb      loc_1400136AF
0x140013777  mov     edx, 75426248h; Tag
0x14001377c  mov     rcx, rbx; P
0x14001377f  call    cs:__imp_ExFreePoolWithTag
0x140013786  nop     dword ptr [rax+rax+00h]
0x14001378b  mov     eax, edi
0x14001378d  mov     rcx, [rbp+57h+var_40]
0x140013791  xor     rcx, rsp; StackCookie
0x140013794  call    __security_check_cookie
0x140013799  add     rsp, 0F8h
0x1400137a0  pop     r14
0x1400137a2  pop     r13
0x1400137a4  pop     rdi
0x1400137a5  pop     rsi
0x1400137a6  pop     rbx
0x1400137a7  pop     rbp
0x1400137a8  retn
```
