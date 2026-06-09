# DiscpGetIScsiSessionList

- ea: `0x180019038`
- end: `0x1800192e2`
- name: `DiscpGetIScsiSessionList`
- size: `682`
- prototype: `__int64 __fastcall(unsigned int *, _DWORD *, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800085c4`
- `0x180009d60`
- `0x18000b444`
- `0x1800185c4`

## callees

- `0x180019038`
- `0x18001a494`

## import_xrefs

- `ISCSIUM!DiscpFreeMemory` at `0x1800192a3`
- `ISCSIUM!DiscpFreeMemory` at `0x1800192b2`
- `ISCSIUM!DiscpFreeMemory` at `0x1800192bc`
- `ISCSIUM!DiscpFreeMemory` at `0x1800192c6`
- `ISCSIUM!DiscpFreeMemory` at `0x1800192a3`
- `ISCSIUM!DiscpFreeMemory` at `0x1800192b2`
- `ISCSIUM!DiscpFreeMemory` at `0x1800192bc`
- `ISCSIUM!DiscpFreeMemory` at `0x1800192c6`
- `ISCSIUM!DiscpParseAllData` at `0x1800190e3`
- `ISCSIUM!DiscpParseAllData` at `0x1800190e3`
- `ISCSIUM!DiscpQueryAllData` at `0x1800190b2`
- `ISCSIUM!DiscpQueryAllData` at `0x1800190b2`

## pseudocode

```c
__int64 __fastcall DiscpGetIScsiSessionList(unsigned int *a1, _DWORD *a2, __int64 a3)
{
  unsigned int v6; // ebx
  unsigned int v7; // r8d
  unsigned int v8; // edx
  __int64 v9; // rcx
  int v10; // r9d
  int v11; // r14d
  unsigned int v12; // edi
  __int64 v13; // rcx
  int v14; // edx
  unsigned int v15; // r15d
  __int64 v16; // rdi
  int v17; // edx
  unsigned int v18; // eax
  __int64 v19; // rcx
  unsigned int v21; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v22; // [rsp+54h] [rbp-45h] BYREF
  unsigned int v23; // [rsp+58h] [rbp-41h] BYREF
  int v24; // [rsp+5Ch] [rbp-3Dh] BYREF
  unsigned int v25; // [rsp+60h] [rbp-39h] BYREF
  int v26; // [rsp+64h] [rbp-35h] BYREF
  int v27; // [rsp+68h] [rbp-31h] BYREF
  int v28; // [rsp+6Ch] [rbp-2Dh] BYREF
  __int64 v29; // [rsp+70h] [rbp-29h] BYREF
  __int64 v30; // [rsp+78h] [rbp-21h] BYREF
  __int64 v31; // [rsp+80h] [rbp-19h] BYREF
  __int64 v32; // [rsp+88h] [rbp-11h] BYREF
  __int64 j; // [rsp+90h] [rbp-9h] BYREF
  __int64 v34; // [rsp+98h] [rbp-1h] BYREF
  __int64 v35[10]; // [rsp+A0h] [rbp+7h] BYREF
  int i; // [rsp+118h] [rbp+7Fh] BYREF

  v29 = 0;
  v25 = 0;
  v23 = 0;
  v31 = 0;
  v30 = 0;
  v32 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v22 = 0;
  v21 = 0;
  i = 0;
  v35[0] = 0;
  v34 = 0;
  j = 0;
  v24 = 0;
  v6 = DiscpQueryAllData(MSiSCSI_InitiatorSessionInfo_GUID, 0, &v29, &v25);
  if ( v6 )
  {
    v19 = 0;
    v29 = 0;
  }
  else
  {
    v6 = DiscpParseAllData(v29, v25, &v23, &v32, &v31, &v30);
    if ( !v6 )
    {
      v7 = v23;
      v8 = 0;
      v9 = 0;
      v10 = 0;
      v22 = 0;
      v11 = 0;
      v21 = 0;
      v12 = 0;
      for ( i = 0; v12 < v23; ++v12 )
      {
        v13 = *(_QWORD *)(v31 + 8LL * v12);
        v14 = *(_DWORD *)(v30 + 4LL * v12);
        i = v10 + 2 + **(unsigned __int16 **)(v32 + 8LL * v12);
        v6 = DiscpValidateAndCopyNodeInfo(
               v13,
               v14,
               (unsigned int)&v26,
               (unsigned int)&v27,
               (__int64)&v28,
               (__int64)&v24,
               0,
               0,
               0,
               0);
        if ( v6 )
        {
          v6 = 0;
          *(_DWORD *)(v30 + 4LL * v12) = 0;
          v9 = v22;
          v8 = v21;
          v10 = i;
        }
        else
        {
          v10 = v28 + i;
          i += v28;
          v9 = ((v26 + 7) & 0xFFFFFFF8) + v22;
          v22 += (v26 + 7) & 0xFFFFFFF8;
          v8 = ((v27 + 7) & 0xFFFFFFF8) + v21;
          v11 += v24;
          v21 = v8;
        }
        v7 = v23;
      }
      v15 = v9 + v10 + v8;
      if ( *a1 >= v15 && a3 && a2 )
      {
        v35[0] = a3;
        v16 = 0;
        v34 = a3 + v9;
        for ( j = a3 + v9 + v8; (unsigned int)v16 < v7; v16 = (unsigned int)(v16 + 1) )
        {
          if ( v6 )
            break;
          v17 = *(_DWORD *)(v30 + 4 * v16);
          if ( v17 )
          {
            v18 = DiscpValidateAndCopyNodeInfo(
                    *(_QWORD *)(v31 + 8 * v16),
                    v17,
                    (unsigned int)&v22,
                    (unsigned int)&v21,
                    (__int64)&i,
                    (__int64)&v24,
                    (__int64)v35,
                    (__int64)&v34,
                    (__int64)&j,
                    0);
            v7 = v23;
            v6 = v18;
          }
        }
      }
      else
      {
        v6 = 122;
      }
      *a1 = v15;
      *a2 = v11;
    }
    v19 = v29;
  }
  if ( v19 )
    DiscpFreeMemory(v19);
  if ( v32 )
  {
    DiscpFreeMemory(v32);
    DiscpFreeMemory(v30);
    DiscpFreeMemory(v31);
  }
  return v6;
}

```

## disassembly

```asm
0x180019038  mov     byte ptr [rsp-8+arg_18], r9b
0x18001903d  push    rbp
0x18001903e  push    rbx
0x18001903f  push    rsi
0x180019040  push    rdi
0x180019041  push    r12
0x180019043  push    r13
0x180019045  push    r14
0x180019047  push    r15
0x180019049  lea     rbp, [rsp-1Fh]
0x18001904e  sub     rsp, 0B8h
0x180019055  xor     r15d, r15d
0x180019058  lea     r9, [rbp+57h+var_90]
0x18001905c  mov     rsi, r8
0x18001905f  mov     [rbp+57h+var_80], r15
0x180019063  mov     r12, rdx
0x180019066  mov     [rbp+57h+var_90], r15d
0x18001906a  mov     r13, rcx
0x18001906d  mov     [rbp+57h+var_98], r15d
0x180019071  lea     r8, [rbp+57h+var_80]
0x180019075  mov     [rbp+57h+var_70], r15
0x180019079  xor     edx, edx
0x18001907b  mov     [rbp+57h+var_78], r15
0x18001907f  lea     rcx, MSiSCSI_InitiatorSessionInfo_GUID
0x180019086  mov     [rbp+57h+var_68], r15
0x18001908a  mov     [rbp+57h+var_8C], r15d
0x18001908e  mov     [rbp+57h+var_88], r15d
0x180019092  mov     [rbp+57h+var_84], r15d
0x180019096  mov     [rbp+57h+var_9C], r15d
0x18001909a  mov     [rbp+57h+var_A0], r15d
0x18001909e  mov     [rbp+57h+arg_18], r15d
0x1800190a2  mov     [rbp+57h+var_50], r15
0x1800190a6  mov     [rbp+57h+var_58], r15
0x1800190aa  mov     [rbp+57h+var_60], r15
0x1800190ae  mov     [rbp+57h+var_94], r15d
0x1800190b2  call    cs:__imp_DiscpQueryAllData
0x1800190b8  mov     ebx, eax
0x1800190ba  test    eax, eax
0x1800190bc  jnz     loc_180019297
0x1800190c2  mov     edx, [rbp+57h+var_90]
0x1800190c5  lea     rax, [rbp+57h+var_78]
0x1800190c9  mov     rcx, [rbp+57h+var_80]
0x1800190cd  lea     r9, [rbp+57h+var_68]
0x1800190d1  mov     [rsp+0F0h+var_C8], rax
0x1800190d6  lea     r8, [rbp+57h+var_98]
0x1800190da  lea     rax, [rbp+57h+var_70]
0x1800190de  mov     [rsp+0F0h+var_D0], rax
0x1800190e3  call    cs:__imp_DiscpParseAllData
0x1800190e9  mov     ebx, eax
0x1800190eb  test    eax, eax
0x1800190ed  jnz     loc_180019291
0x1800190f3  mov     r8d, [rbp+57h+var_98]
0x1800190f7  mov     edx, r15d
0x1800190fa  mov     ecx, r15d
0x1800190fd  mov     r9d, r15d
0x180019100  mov     [rbp+57h+var_9C], ecx
0x180019103  mov     r14d, r15d
0x180019106  mov     [rbp+57h+var_A0], edx
0x180019109  mov     edi, r15d
0x18001910c  mov     [rbp+57h+arg_18], r15d
0x180019110  test    r8d, r8d
0x180019113  jz      loc_1800191E6
0x180019119  mov     rax, [rbp+57h+var_70]
0x18001911d  add     r9d, 2
0x180019121  mov     [rsp+0F0h+var_A8], 0
0x180019126  mov     [rsp+0F0h+var_B0], 0
0x18001912f  mov     r15d, edi
0x180019132  mov     [rsp+0F0h+var_B8], 0
0x18001913b  mov     [rsp+0F0h+var_C0], 0
0x180019144  mov     rcx, [rax+r15*8]
0x180019148  mov     rax, [rbp+57h+var_78]
0x18001914c  mov     edx, [rax+r15*4]
0x180019150  mov     rax, [rbp+57h+var_68]
0x180019154  mov     r8, [rax+r15*8]
0x180019158  lea     rax, [rbp+57h+var_94]
0x18001915c  mov     [rsp+0F0h+var_C8], rax
0x180019161  lea     rax, [rbp+57h+var_84]
0x180019165  mov     [rsp+0F0h+var_D0], rax
0x18001916a  movzx   r8d, word ptr [r8]
0x18001916e  add     r8d, r9d
0x180019171  lea     r9, [rbp+57h+var_88]
0x180019175  mov     [rbp+57h+arg_18], r8d
0x180019179  lea     r8, [rbp+57h+var_8C]
0x18001917d  call    DiscpValidateAndCopyNodeInfo
0x180019182  mov     ebx, eax
0x180019184  test    eax, eax
0x180019186  jnz     short loc_1800191BF
0x180019188  mov     ecx, [rbp+57h+var_9C]
0x18001918b  mov     edx, 0FFFFFFF8h
0x180019190  mov     r9d, [rbp+57h+arg_18]
0x180019194  add     r9d, [rbp+57h+var_84]
0x180019198  mov     eax, [rbp+57h+var_8C]
0x18001919b  add     eax, 7
0x18001919e  mov     [rbp+57h+arg_18], r9d
0x1800191a2  and     eax, edx
0x1800191a4  add     ecx, eax
0x1800191a6  mov     eax, [rbp+57h+var_88]
0x1800191a9  add     eax, 7
0x1800191ac  mov     [rbp+57h+var_9C], ecx
0x1800191af  and     eax, edx
0x1800191b1  mov     edx, [rbp+57h+var_A0]
0x1800191b4  add     edx, eax
0x1800191b6  add     r14d, [rbp+57h+var_94]
0x1800191ba  mov     [rbp+57h+var_A0], edx
0x1800191bd  jmp     short loc_1800191D7
0x1800191bf  mov     rax, [rbp+57h+var_78]
0x1800191c3  xor     ebx, ebx
0x1800191c5  mov     dword ptr [rax+r15*4], 0
0x1800191cd  mov     ecx, [rbp+57h+var_9C]
0x1800191d0  mov     edx, [rbp+57h+var_A0]
0x1800191d3  mov     r9d, [rbp+57h+arg_18]
0x1800191d7  mov     r8d, [rbp+57h+var_98]
0x1800191db  inc     edi
0x1800191dd  cmp     edi, r8d
0x1800191e0  jb      loc_180019119
0x1800191e6  lea     r15d, [r9+rdx]
0x1800191ea  add     r15d, ecx
0x1800191ed  cmp     [r13+0], r15d
0x1800191f1  jb      loc_180019284
0x1800191f7  test    rsi, rsi
0x1800191fa  jz      loc_180019284
0x180019200  test    r12, r12
0x180019203  jz      short loc_180019284
0x180019205  add     rcx, rsi
0x180019208  mov     eax, edx
0x18001920a  add     rax, rcx
0x18001920d  mov     [rbp+57h+var_50], rsi
0x180019211  xor     edi, edi
0x180019213  mov     [rbp+57h+var_58], rcx
0x180019217  mov     [rbp+57h+var_60], rax
0x18001921b  test    r8d, r8d
0x18001921e  jz      short loc_180019289
0x180019220  test    ebx, ebx
0x180019222  jnz     short loc_180019289
0x180019224  mov     rax, [rbp+57h+var_78]
0x180019228  mov     edx, [rax+rdi*4]
0x18001922b  test    edx, edx
0x18001922d  jz      short loc_18001927B
0x18001922f  mov     rcx, [rbp+57h+var_70]
0x180019233  lea     rax, [rbp+57h+var_60]
0x180019237  mov     [rsp+0F0h+var_A8], bl
0x18001923b  lea     r9, [rbp+57h+var_A0]
0x18001923f  mov     [rsp+0F0h+var_B0], rax
0x180019244  lea     r8, [rbp+57h+var_9C]
0x180019248  lea     rax, [rbp+57h+var_58]
0x18001924c  mov     rcx, [rcx+rdi*8]
0x180019250  mov     [rsp+0F0h+var_B8], rax
0x180019255  lea     rax, [rbp+57h+var_50]
0x180019259  mov     [rsp+0F0h+var_C0], rax
0x18001925e  lea     rax, [rbp+57h+var_94]
0x180019262  mov     [rsp+0F0h+var_C8], rax
0x180019267  lea     rax, [rbp+57h+arg_18]
0x18001926b  mov     [rsp+0F0h+var_D0], rax
0x180019270  call    DiscpValidateAndCopyNodeInfo
0x180019275  mov     r8d, [rbp+57h+var_98]
0x180019279  mov     ebx, eax
0x18001927b  inc     edi
0x18001927d  cmp     edi, r8d
0x180019280  jb      short loc_180019220
0x180019282  jmp     short loc_180019289
0x180019284  mov     ebx, 7Ah ; 'z'
0x180019289  mov     [r13+0], r15d
0x18001928d  mov     [r12], r14d
0x180019291  mov     rcx, [rbp+57h+var_80]
0x180019295  jmp     short loc_18001929E
0x180019297  mov     rcx, r15
0x18001929a  mov     [rbp+57h+var_80], rcx
0x18001929e  test    rcx, rcx
0x1800192a1  jz      short loc_1800192A9
0x1800192a3  call    cs:__imp_DiscpFreeMemory
0x1800192a9  mov     rcx, [rbp+57h+var_68]
0x1800192ad  test    rcx, rcx
0x1800192b0  jz      short loc_1800192CC
0x1800192b2  call    cs:__imp_DiscpFreeMemory
0x1800192b8  mov     rcx, [rbp+57h+var_78]
0x1800192bc  call    cs:__imp_DiscpFreeMemory
0x1800192c2  mov     rcx, [rbp+57h+var_70]
0x1800192c6  call    cs:__imp_DiscpFreeMemory
0x1800192cc  mov     eax, ebx
0x1800192ce  add     rsp, 0B8h
0x1800192d5  pop     r15
0x1800192d7  pop     r14
0x1800192d9  pop     r13
0x1800192db  pop     r12
0x1800192dd  pop     rdi
0x1800192de  pop     rsi
0x1800192df  pop     rbx
0x1800192e0  pop     rbp
0x1800192e1  retn
```
