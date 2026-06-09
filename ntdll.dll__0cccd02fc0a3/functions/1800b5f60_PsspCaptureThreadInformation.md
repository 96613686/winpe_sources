# PsspCaptureThreadInformation

- ea: `0x1800b5f60`
- end: `0x1800b6360`
- name: `PsspCaptureThreadInformation`
- size: `1024`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18009b1f0`

## callees

- `0x1800b5f60`
- `0x1800b6368`
- `0x1800b6870`
- `0x1800b7f5c`
- `0x18015e4b0`
- `0x18015e5d0`
- `0x18015e770`
- `0x18015e7d0`
- `0x18015e810`
- `0x18015ec10`
- `0x1801602c0`
- `0x180162000`
- `0x18016f030`

## pseudocode

```c
__int64 __fastcall PsspCaptureThreadInformation(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  __int64 v4; // r14
  __int64 **v7; // rbx
  __int64 *v8; // rdi
  unsigned int v9; // r15d
  int v10; // r12d
  unsigned int v11; // edx
  int NextThread; // eax
  int v13; // esi
  int v14; // r14d
  unsigned __int64 v15; // rcx
  int Section; // edi
  __int64 **v17; // rsi
  __int64 i; // r15
  int v19; // eax
  int ExtendedContextLength; // eax
  int *v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+20h] [rbp-E0h]
  unsigned int v24; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v26; // [rsp+60h] [rbp-A0h]
  unsigned int v27; // [rsp+64h] [rbp-9Ch]
  __int64 *v28; // [rsp+68h] [rbp-98h] BYREF
  __int64 v29; // [rsp+70h] [rbp-90h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp-88h]
  __int64 v31; // [rsp+80h] [rbp-80h] BYREF
  int v32; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v33[12]; // [rsp+8Ch] [rbp-74h]
  _BYTE v34[24]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v35; // [rsp+B0h] [rbp-50h]
  _WORD v36[264]; // [rsp+C0h] [rbp-40h] BYREF

  v4 = 0;
  v27 = a3;
  v35 = a2;
  v28 = 0;
  Handle = 0;
  *(_DWORD *)&v33[8] = 0;
  v29 = 0;
  v25 = 0;
  memset(v34, 0, sizeof(v34));
  v31 = 0;
  v26 = a4;
  memset_thunk_772440563353939046(v36, 0, 0x210u);
  v32 = 0;
  *(_QWORD *)v33 = a3 & 0x100;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = (*(_DWORD *)v33 != 0 ? 72 : 64) | (a3 >> 7) & 8;
  v24 = v11;
  while ( 1 )
  {
    LODWORD(v22) = 0;
    NextThread = ZwGetNextThread(v35, v4, v11, 0, v22, &v31);
    v13 = NextThread;
    if ( NextThread == -2147483622 )
    {
      if ( v9 )
      {
        v14 = 0;
        v24 = 0;
        if ( *(_DWORD *)v33 )
        {
          if ( (v27 & 0x200) == 0
            || (ExtendedContextLength = RtlGetExtendedContextLength(v26, &v24), v14 = v24, ExtendedContextLength < 0) )
          {
            v14 = 1232;
          }
        }
        *(_DWORD *)(a1 + 1024) = v14;
        v15 = v9 * (unsigned __int64)(((v14 + 15) & 0xFFFFFFF0) + 128);
        if ( v15 > 0xFFFFFFFF )
        {
          PsspFreeLinkedHandleList(v7);
          return 3221225621LL;
        }
        *(_QWORD *)&v33[4] = (unsigned int)(v10 + v15);
        Section = NtCreateSection();
        if ( Section >= 0 )
        {
          v29 = 0;
          v25 = 0;
          Section = ZwMapViewOfSection(Handle, -1, &v29, 0, 0, 0, &v25, 1, 0, 4);
          if ( Section >= 0 )
          {
            *(_QWORD *)v34 = v29;
            *(_QWORD *)&v34[12] = 0;
            v17 = v7;
            *(_DWORD *)&v34[8] = v25;
            while ( v17 )
            {
              for ( i = 0; (unsigned int)i < *((unsigned __int16 *)v17 + 5); i = (unsigned int)(i + 1) )
              {
                v31 = *((unsigned int *)v17 + i + 3);
                v19 = PsspDumpThread((unsigned int)v34, v27, v26, v14, v23, v31);
                Section = v19;
                if ( v19 == -1073741789 )
                  break;
                if ( v19 < 0 )
                {
                  NtUnmapViewOfSection(-1);
                  goto LABEL_36;
                }
              }
              if ( Section < 0 )
                break;
              v17 = (__int64 **)*v17;
            }
            NtUnmapViewOfSection(-1);
            PsspFreeLinkedHandleList(v7);
            *(_DWORD *)(a1 + 992) = *(_DWORD *)&v34[16];
            *(_QWORD *)(a1 + 1000) = *(unsigned int *)&v34[12];
            *(_QWORD *)(a1 + 1008) = Handle;
            *(_QWORD *)(a1 + 1016) = MEMORY[0x7FFE0014];
            return 0;
          }
LABEL_36:
          NtClose(Handle);
        }
        PsspFreeLinkedHandleList(v7);
        return (unsigned int)Section;
      }
      return 0;
    }
    if ( NextThread < 0 )
      goto LABEL_38;
    v4 = v31;
    v22 = &v32;
    if ( (int)ZwQueryInformationThread() >= 0 )
      v10 += (v36[0] + 15) & 0xFFFFFFF0;
    if ( !v8 || *((_WORD *)v8 + 5) >= *((_WORD *)v8 + 4) )
      break;
LABEL_8:
    v11 = v24;
    *((_DWORD *)v8 + (unsigned __int16)(*((_WORD *)v8 + 5))++ + 3) = v31;
    ++v9;
  }
  v25 = 1;
  v28 = 0;
  v13 = ZwAllocateVirtualMemory(-1, &v28, 0, &v25, 4096, 4);
  if ( v13 >= 0 )
  {
    if ( v7 )
    {
      *v8 = (__int64)v28;
      v8 = v28;
    }
    else
    {
      v8 = v28;
      v7 = (__int64 **)v28;
    }
    *((_WORD *)v8 + 4) = (unsigned __int64)(v25 - 16) >> 2;
    *((_WORD *)v8 + 5) = 0;
    goto LABEL_8;
  }
LABEL_38:
  PsspFreeLinkedHandleList(v7);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800b5f60  mov     [rsp-8+arg_10], rbx
0x1800b5f65  push    rbp
0x1800b5f66  push    rsi
0x1800b5f67  push    rdi
0x1800b5f68  push    r12
0x1800b5f6a  push    r13
0x1800b5f6c  push    r14
0x1800b5f6e  push    r15
0x1800b5f70  lea     rbp, [rsp-1E0h]
0x1800b5f78  sub     rsp, 2E0h
0x1800b5f7f  mov     rax, cs:__security_cookie
0x1800b5f86  xor     rax, rsp
0x1800b5f89  mov     [rbp+210h+var_40], rax
0x1800b5f90  xor     r14d, r14d
0x1800b5f93  mov     [rsp+310h+var_2AC], r8d
0x1800b5f98  mov     esi, r8d
0x1800b5f9b  mov     [rbp+210h+var_260], rdx
0x1800b5f9f  mov     r13, rcx
0x1800b5fa2  mov     [rsp+310h+var_2A8], r14
0x1800b5fa7  xorps   xmm0, xmm0
0x1800b5faa  mov     [rsp+310h+Handle], r14
0x1800b5faf  xor     eax, eax
0x1800b5fb1  mov     [rbp+210h+var_280], r14
0x1800b5fb5  xor     edx, edx; Val
0x1800b5fb7  mov     [rsp+310h+var_2A0], r14
0x1800b5fbc  mov     r8d, 210h; Size
0x1800b5fc2  mov     [rbp+210h+var_268], rax
0x1800b5fc6  lea     rcx, [rbp+210h+var_250]; void *
0x1800b5fca  mov     [rsp+310h+var_2B8], r14
0x1800b5fcf  movups  [rbp+210h+var_278], xmm0
0x1800b5fd3  mov     [rbp+210h+var_290], r14
0x1800b5fd7  mov     [rsp+310h+var_2B0], r9d
0x1800b5fdc  call    memset$thunk$772440563353939046
0x1800b5fe1  mov     edx, esi
0x1800b5fe3  mov     [rbp+210h+var_288], r14d
0x1800b5fe7  shr     edx, 7
0x1800b5fea  mov     eax, esi
0x1800b5fec  and     eax, 100h
0x1800b5ff1  and     edx, 8
0x1800b5ff4  mov     [rbp+210h+var_284], eax
0x1800b5ff7  mov     ebx, r14d
0x1800b5ffa  neg     eax
0x1800b5ffc  mov     edi, r14d
0x1800b5fff  mov     r15d, r14d
0x1800b6002  mov     r12d, r14d
0x1800b6005  sbb     ecx, ecx
0x1800b6007  and     ecx, 8
0x1800b600a  add     ecx, 40h ; '@'
0x1800b600d  or      edx, ecx
0x1800b600f  mov     [rsp+310h+var_2C0], edx
0x1800b6013  mov     rcx, [rbp+210h+var_260]
0x1800b6017  lea     rax, [rbp+210h+var_290]
0x1800b601b  mov     r8d, edx
0x1800b601e  mov     [rsp+310h+var_2E8], rax
0x1800b6023  xor     r9d, r9d
0x1800b6026  mov     dword ptr [rsp+310h+var_2F0], 0
0x1800b602e  mov     rdx, r14
0x1800b6031  call    ZwGetNextThread
0x1800b6036  mov     esi, eax
0x1800b6038  cmp     eax, 8000001Ah
0x1800b603d  jz      short loc_1800B60B3
0x1800b603f  test    eax, eax
0x1800b6041  js      loc_1800B6351
0x1800b6047  mov     r14, [rbp+210h+var_290]
0x1800b604b  lea     rax, [rbp+210h+var_288]
0x1800b604f  mov     rcx, r14
0x1800b6052  mov     [rsp+310h+var_2F0], rax
0x1800b6057  mov     r9d, 210h
0x1800b605d  lea     r8, [rbp+210h+var_250]
0x1800b6061  mov     edx, 26h ; '&'
0x1800b6066  call    ZwQueryInformationThread
0x1800b606b  test    eax, eax
0x1800b606d  js      short loc_1800B607C
0x1800b606f  movzx   eax, [rbp+210h+var_250]
0x1800b6073  add     eax, 0Fh
0x1800b6076  and     eax, 0FFFFFFF0h
0x1800b6079  add     r12d, eax
0x1800b607c  test    rdi, rdi
0x1800b607f  jz      loc_1800B6200
0x1800b6085  movzx   eax, word ptr [rdi+8]
0x1800b6089  cmp     [rdi+0Ah], ax
0x1800b608d  jnb     loc_1800B6200
0x1800b6093  mov     eax, dword ptr [rbp+210h+var_290]
0x1800b6096  movzx   ecx, word ptr [rdi+0Ah]
0x1800b609a  mov     edx, [rsp+310h+var_2C0]
0x1800b609e  mov     [rdi+rcx*4+0Ch], eax
0x1800b60a2  mov     eax, 1
0x1800b60a7  add     [rdi+0Ah], ax
0x1800b60ab  add     r15d, eax
0x1800b60ae  jmp     loc_1800B6013
0x1800b60b3  xor     esi, esi
0x1800b60b5  test    r15d, r15d
0x1800b60b8  jz      loc_1800B6303
0x1800b60be  mov     r14d, esi
0x1800b60c1  mov     [rsp+310h+var_2C0], esi
0x1800b60c5  cmp     [rbp+210h+var_284], esi
0x1800b60c8  jz      short loc_1800B60DE
0x1800b60ca  test    [rsp+310h+var_2AC], 200h
0x1800b60d2  jnz     loc_1800B630A
0x1800b60d8  mov     r14d, 4D0h
0x1800b60de  lea     ecx, [r14+0Fh]
0x1800b60e2  mov     eax, r15d
0x1800b60e5  and     ecx, 0FFFFFFF0h
0x1800b60e8  mov     [r13+400h], r14d
0x1800b60ef  sub     ecx, 0FFFFFF80h
0x1800b60f2  imul    rcx, rax
0x1800b60f6  mov     eax, 0FFFFFFFFh
0x1800b60fb  cmp     rcx, rax
0x1800b60fe  ja      loc_1800B6277
0x1800b6104  add     ecx, r12d
0x1800b6107  mov     [rsp+310h+var_2E0], rsi
0x1800b610c  mov     [rbp+210h+var_280], rcx
0x1800b6110  lea     r9, [rbp+210h+var_280]
0x1800b6114  mov     r15d, 4
0x1800b611a  mov     dword ptr [rsp+310h+var_2E8], 8000000h
0x1800b6122  lea     rcx, [rsp+310h+Handle]
0x1800b6127  mov     dword ptr [rsp+310h+var_2F0], r15d
0x1800b612c  lea     r8, a0_3; "0"
0x1800b6133  mov     edx, 0F0007h
0x1800b6138  call    NtCreateSection
0x1800b613d  mov     edi, eax
0x1800b613f  test    eax, eax
0x1800b6141  js      loc_1800B6342
0x1800b6147  mov     rcx, [rsp+310h+Handle]
0x1800b614c  lea     rax, [rsp+310h+var_2B8]
0x1800b6151  mov     [rsp+310h+var_2C8], r15d
0x1800b6156  lea     r12d, [r15-3]
0x1800b615a  mov     [rsp+310h+var_2D0], esi
0x1800b615e  lea     r8, [rsp+310h+var_2A0]
0x1800b6163  mov     [rsp+310h+var_2D8], r12d
0x1800b6168  xor     r9d, r9d
0x1800b616b  mov     [rsp+310h+var_2E0], rax
0x1800b6170  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800b6174  mov     [rsp+310h+var_2E8], rsi
0x1800b6179  mov     [rsp+310h+var_2F0], rsi
0x1800b617e  mov     [rsp+310h+var_2A0], rsi
0x1800b6183  mov     [rsp+310h+var_2B8], rsi
0x1800b6188  call    ZwMapViewOfSection
0x1800b618d  mov     edi, eax
0x1800b618f  test    eax, eax
0x1800b6191  js      loc_1800B6338
0x1800b6197  mov     rax, [rsp+310h+var_2A0]
0x1800b619c  mov     qword ptr [rbp+210h+var_278], rax
0x1800b61a0  mov     eax, dword ptr [rsp+310h+var_2B8]
0x1800b61a4  mov     qword ptr [rbp+210h+var_278+0Ch], rsi
0x1800b61a8  mov     rsi, rbx
0x1800b61ab  mov     dword ptr [rbp+210h+var_278+8], eax
0x1800b61ae  test    rsi, rsi
0x1800b61b1  jz      loc_1800B62BE
0x1800b61b7  xor     r15d, r15d
0x1800b61ba  movzx   eax, word ptr [rsi+0Ah]
0x1800b61be  cmp     r15d, eax
0x1800b61c1  jnb     loc_1800B626B
0x1800b61c7  mov     ecx, [rsi+r15*4+0Ch]
0x1800b61cc  mov     r9d, r14d
0x1800b61cf  mov     r8d, [rsp+310h+var_2B0]
0x1800b61d4  mov     edx, [rsp+310h+var_2AC]
0x1800b61d8  mov     [rbp+210h+var_290], rcx
0x1800b61dc  mov     [rsp+310h+var_2E8], rcx
0x1800b61e1  lea     rcx, [rbp+210h+var_278]
0x1800b61e5  call    PsspDumpThread
0x1800b61ea  mov     edi, eax
0x1800b61ec  cmp     eax, 0C0000023h
0x1800b61f1  jz      short loc_1800B626B
0x1800b61f3  test    eax, eax
0x1800b61f5  js      loc_1800B632A
0x1800b61fb  add     r15d, r12d
0x1800b61fe  jmp     short loc_1800B61BA
0x1800b6200  mov     dword ptr [rsp+310h+var_2E8], 4
0x1800b6208  lea     r9, [rsp+310h+var_2B8]
0x1800b620d  xor     r8d, r8d
0x1800b6210  mov     dword ptr [rsp+310h+var_2F0], 1000h
0x1800b6218  lea     rdx, [rsp+310h+var_2A8]
0x1800b621d  mov     [rsp+310h+var_2B8], 1
0x1800b6226  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800b622a  mov     [rsp+310h+var_2A8], 0
0x1800b6233  call    ZwAllocateVirtualMemory
0x1800b6238  mov     esi, eax
0x1800b623a  test    eax, eax
0x1800b623c  js      loc_1800B6351
0x1800b6242  test    rbx, rbx
0x1800b6245  jnz     short loc_1800B62AF
0x1800b6247  mov     rdi, [rsp+310h+var_2A8]
0x1800b624c  mov     rbx, rdi
0x1800b624f  mov     rax, [rsp+310h+var_2B8]
0x1800b6254  add     rax, 0FFFFFFFFFFFFFFF0h
0x1800b6258  shr     rax, 2
0x1800b625c  mov     [rdi+8], ax
0x1800b6260  xor     eax, eax
0x1800b6262  mov     [rdi+0Ah], ax
0x1800b6266  jmp     loc_1800B6093
0x1800b626b  test    edi, edi
0x1800b626d  js      short loc_1800B62BE
0x1800b626f  mov     rsi, [rsi]
0x1800b6272  jmp     loc_1800B61AE
0x1800b6277  mov     rcx, rbx
0x1800b627a  call    PsspFreeLinkedHandleList
0x1800b627f  mov     eax, 0C0000095h
0x1800b6284  mov     rcx, [rbp+210h+var_40]
0x1800b628b  xor     rcx, rsp; StackCookie
0x1800b628e  call    __security_check_cookie
0x1800b6293  mov     rbx, [rsp+310h+arg_10]
0x1800b629b  add     rsp, 2E0h
0x1800b62a2  pop     r15
0x1800b62a4  pop     r14
0x1800b62a6  pop     r13
0x1800b62a8  pop     r12
0x1800b62aa  pop     rdi
0x1800b62ab  pop     rsi
0x1800b62ac  pop     rbp
0x1800b62ad  retn
0x1800b62af  mov     rax, [rsp+310h+var_2A8]
0x1800b62b4  mov     [rdi], rax
0x1800b62b7  mov     rdi, [rsp+310h+var_2A8]
0x1800b62bc  jmp     short loc_1800B624F
0x1800b62be  mov     rdx, [rsp+310h+var_2A0]
0x1800b62c3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800b62c7  call    NtUnmapViewOfSection
0x1800b62cc  mov     rcx, rbx
0x1800b62cf  call    PsspFreeLinkedHandleList
0x1800b62d4  mov     eax, dword ptr [rbp+210h+var_268]
0x1800b62d7  mov     [r13+3E0h], eax
0x1800b62de  mov     eax, dword ptr [rbp+210h+var_278+0Ch]
0x1800b62e1  mov     [r13+3E8h], rax
0x1800b62e8  mov     rax, [rsp+310h+Handle]
0x1800b62ed  mov     [r13+3F0h], rax
0x1800b62f4  mov     eax, 7FFE0014h
0x1800b62f9  mov     rax, [rax]
0x1800b62fc  mov     [r13+3F8h], rax
0x1800b6303  xor     eax, eax
0x1800b6305  jmp     loc_1800B6284
0x1800b630a  mov     ecx, [rsp+310h+var_2B0]
0x1800b630e  lea     rdx, [rsp+310h+var_2C0]
0x1800b6313  call    RtlGetExtendedContextLength
0x1800b6318  mov     r14d, [rsp+310h+var_2C0]
0x1800b631d  test    eax, eax
0x1800b631f  jns     loc_1800B60DE
0x1800b6325  jmp     loc_1800B60D8
0x1800b632a  mov     rdx, [rsp+310h+var_2A0]
0x1800b632f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800b6333  call    NtUnmapViewOfSection
0x1800b6338  mov     rcx, [rsp+310h+Handle]; Handle
0x1800b633d  call    NtClose
0x1800b6342  mov     rcx, rbx
0x1800b6345  call    PsspFreeLinkedHandleList
0x1800b634a  mov     eax, edi
0x1800b634c  jmp     loc_1800B6284
0x1800b6351  mov     rcx, rbx
0x1800b6354  call    PsspFreeLinkedHandleList
0x1800b6359  mov     eax, esi
0x1800b635b  jmp     loc_1800B6284
```
