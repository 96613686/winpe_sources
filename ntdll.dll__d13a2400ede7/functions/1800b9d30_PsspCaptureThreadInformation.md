# PsspCaptureThreadInformation

- ea: `0x1800b9d30`
- end: `0x1800ba130`
- name: `PsspCaptureThreadInformation`
- size: `1024`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1800a7640`

## callees

- `0x1800b9d30`
- `0x1800ba138`
- `0x1800ba650`
- `0x1800bbcfc`
- `0x18015ecc0`
- `0x18015ede0`
- `0x18015ef80`
- `0x18015efe0`
- `0x18015f020`
- `0x18015f420`
- `0x180160ad0`
- `0x180162810`
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
0x1800b9d30  mov     [rsp-8+arg_10], rbx
0x1800b9d35  push    rbp
0x1800b9d36  push    rsi
0x1800b9d37  push    rdi
0x1800b9d38  push    r12
0x1800b9d3a  push    r13
0x1800b9d3c  push    r14
0x1800b9d3e  push    r15
0x1800b9d40  lea     rbp, [rsp-1E0h]
0x1800b9d48  sub     rsp, 2E0h
0x1800b9d4f  mov     rax, cs:__security_cookie
0x1800b9d56  xor     rax, rsp
0x1800b9d59  mov     [rbp+210h+var_40], rax
0x1800b9d60  xor     r14d, r14d
0x1800b9d63  mov     [rsp+310h+var_2AC], r8d
0x1800b9d68  mov     esi, r8d
0x1800b9d6b  mov     [rbp+210h+var_260], rdx
0x1800b9d6f  mov     r13, rcx
0x1800b9d72  mov     [rsp+310h+var_2A8], r14
0x1800b9d77  xorps   xmm0, xmm0
0x1800b9d7a  mov     [rsp+310h+Handle], r14
0x1800b9d7f  xor     eax, eax
0x1800b9d81  mov     [rbp+210h+var_280], r14
0x1800b9d85  xor     edx, edx; Val
0x1800b9d87  mov     [rsp+310h+var_2A0], r14
0x1800b9d8c  mov     r8d, 210h; Size
0x1800b9d92  mov     [rbp+210h+var_268], rax
0x1800b9d96  lea     rcx, [rbp+210h+var_250]; void *
0x1800b9d9a  mov     [rsp+310h+var_2B8], r14
0x1800b9d9f  movups  [rbp+210h+var_278], xmm0
0x1800b9da3  mov     [rbp+210h+var_290], r14
0x1800b9da7  mov     [rsp+310h+var_2B0], r9d
0x1800b9dac  call    memset$thunk$772440563353939046
0x1800b9db1  mov     edx, esi
0x1800b9db3  mov     [rbp+210h+var_288], r14d
0x1800b9db7  shr     edx, 7
0x1800b9dba  mov     eax, esi
0x1800b9dbc  and     eax, 100h
0x1800b9dc1  and     edx, 8
0x1800b9dc4  mov     [rbp+210h+var_284], eax
0x1800b9dc7  mov     ebx, r14d
0x1800b9dca  neg     eax
0x1800b9dcc  mov     edi, r14d
0x1800b9dcf  mov     r15d, r14d
0x1800b9dd2  mov     r12d, r14d
0x1800b9dd5  sbb     ecx, ecx
0x1800b9dd7  and     ecx, 8
0x1800b9dda  add     ecx, 40h ; '@'
0x1800b9ddd  or      edx, ecx
0x1800b9ddf  mov     [rsp+310h+var_2C0], edx
0x1800b9de3  mov     rcx, [rbp+210h+var_260]
0x1800b9de7  lea     rax, [rbp+210h+var_290]
0x1800b9deb  mov     r8d, edx
0x1800b9dee  mov     [rsp+310h+var_2E8], rax
0x1800b9df3  xor     r9d, r9d
0x1800b9df6  mov     dword ptr [rsp+310h+var_2F0], 0
0x1800b9dfe  mov     rdx, r14
0x1800b9e01  call    ZwGetNextThread
0x1800b9e06  mov     esi, eax
0x1800b9e08  cmp     eax, 8000001Ah
0x1800b9e0d  jz      short loc_1800B9E83
0x1800b9e0f  test    eax, eax
0x1800b9e11  js      loc_1800BA121
0x1800b9e17  mov     r14, [rbp+210h+var_290]
0x1800b9e1b  lea     rax, [rbp+210h+var_288]
0x1800b9e1f  mov     rcx, r14
0x1800b9e22  mov     [rsp+310h+var_2F0], rax
0x1800b9e27  mov     r9d, 210h
0x1800b9e2d  lea     r8, [rbp+210h+var_250]
0x1800b9e31  mov     edx, 26h ; '&'
0x1800b9e36  call    ZwQueryInformationThread
0x1800b9e3b  test    eax, eax
0x1800b9e3d  js      short loc_1800B9E4C
0x1800b9e3f  movzx   eax, [rbp+210h+var_250]
0x1800b9e43  add     eax, 0Fh
0x1800b9e46  and     eax, 0FFFFFFF0h
0x1800b9e49  add     r12d, eax
0x1800b9e4c  test    rdi, rdi
0x1800b9e4f  jz      loc_1800B9FD0
0x1800b9e55  movzx   eax, word ptr [rdi+8]
0x1800b9e59  cmp     [rdi+0Ah], ax
0x1800b9e5d  jnb     loc_1800B9FD0
0x1800b9e63  mov     eax, dword ptr [rbp+210h+var_290]
0x1800b9e66  movzx   ecx, word ptr [rdi+0Ah]
0x1800b9e6a  mov     edx, [rsp+310h+var_2C0]
0x1800b9e6e  mov     [rdi+rcx*4+0Ch], eax
0x1800b9e72  mov     eax, 1
0x1800b9e77  add     [rdi+0Ah], ax
0x1800b9e7b  add     r15d, eax
0x1800b9e7e  jmp     loc_1800B9DE3
0x1800b9e83  xor     esi, esi
0x1800b9e85  test    r15d, r15d
0x1800b9e88  jz      loc_1800BA0D3
0x1800b9e8e  mov     r14d, esi
0x1800b9e91  mov     [rsp+310h+var_2C0], esi
0x1800b9e95  cmp     [rbp+210h+var_284], esi
0x1800b9e98  jz      short loc_1800B9EAE
0x1800b9e9a  test    [rsp+310h+var_2AC], 200h
0x1800b9ea2  jnz     loc_1800BA0DA
0x1800b9ea8  mov     r14d, 4D0h
0x1800b9eae  lea     ecx, [r14+0Fh]
0x1800b9eb2  mov     eax, r15d
0x1800b9eb5  and     ecx, 0FFFFFFF0h
0x1800b9eb8  mov     [r13+400h], r14d
0x1800b9ebf  sub     ecx, 0FFFFFF80h
0x1800b9ec2  imul    rcx, rax
0x1800b9ec6  mov     eax, 0FFFFFFFFh
0x1800b9ecb  cmp     rcx, rax
0x1800b9ece  ja      loc_1800BA047
0x1800b9ed4  add     ecx, r12d
0x1800b9ed7  mov     [rsp+310h+var_2E0], rsi
0x1800b9edc  mov     [rbp+210h+var_280], rcx
0x1800b9ee0  lea     r9, [rbp+210h+var_280]
0x1800b9ee4  mov     r15d, 4
0x1800b9eea  mov     dword ptr [rsp+310h+var_2E8], 8000000h
0x1800b9ef2  lea     rcx, [rsp+310h+Handle]
0x1800b9ef7  mov     dword ptr [rsp+310h+var_2F0], r15d
0x1800b9efc  lea     r8, a0_3; "0"
0x1800b9f03  mov     edx, 0F0007h
0x1800b9f08  call    NtCreateSection
0x1800b9f0d  mov     edi, eax
0x1800b9f0f  test    eax, eax
0x1800b9f11  js      loc_1800BA112
0x1800b9f17  mov     rcx, [rsp+310h+Handle]
0x1800b9f1c  lea     rax, [rsp+310h+var_2B8]
0x1800b9f21  mov     [rsp+310h+var_2C8], r15d
0x1800b9f26  lea     r12d, [r15-3]
0x1800b9f2a  mov     [rsp+310h+var_2D0], esi
0x1800b9f2e  lea     r8, [rsp+310h+var_2A0]
0x1800b9f33  mov     [rsp+310h+var_2D8], r12d
0x1800b9f38  xor     r9d, r9d
0x1800b9f3b  mov     [rsp+310h+var_2E0], rax
0x1800b9f40  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800b9f44  mov     [rsp+310h+var_2E8], rsi
0x1800b9f49  mov     [rsp+310h+var_2F0], rsi
0x1800b9f4e  mov     [rsp+310h+var_2A0], rsi
0x1800b9f53  mov     [rsp+310h+var_2B8], rsi
0x1800b9f58  call    ZwMapViewOfSection
0x1800b9f5d  mov     edi, eax
0x1800b9f5f  test    eax, eax
0x1800b9f61  js      loc_1800BA108
0x1800b9f67  mov     rax, [rsp+310h+var_2A0]
0x1800b9f6c  mov     qword ptr [rbp+210h+var_278], rax
0x1800b9f70  mov     eax, dword ptr [rsp+310h+var_2B8]
0x1800b9f74  mov     qword ptr [rbp+210h+var_278+0Ch], rsi
0x1800b9f78  mov     rsi, rbx
0x1800b9f7b  mov     dword ptr [rbp+210h+var_278+8], eax
0x1800b9f7e  test    rsi, rsi
0x1800b9f81  jz      loc_1800BA08E
0x1800b9f87  xor     r15d, r15d
0x1800b9f8a  movzx   eax, word ptr [rsi+0Ah]
0x1800b9f8e  cmp     r15d, eax
0x1800b9f91  jnb     loc_1800BA03B
0x1800b9f97  mov     ecx, [rsi+r15*4+0Ch]
0x1800b9f9c  mov     r9d, r14d
0x1800b9f9f  mov     r8d, [rsp+310h+var_2B0]
0x1800b9fa4  mov     edx, [rsp+310h+var_2AC]
0x1800b9fa8  mov     [rbp+210h+var_290], rcx
0x1800b9fac  mov     [rsp+310h+var_2E8], rcx
0x1800b9fb1  lea     rcx, [rbp+210h+var_278]
0x1800b9fb5  call    PsspDumpThread
0x1800b9fba  mov     edi, eax
0x1800b9fbc  cmp     eax, 0C0000023h
0x1800b9fc1  jz      short loc_1800BA03B
0x1800b9fc3  test    eax, eax
0x1800b9fc5  js      loc_1800BA0FA
0x1800b9fcb  add     r15d, r12d
0x1800b9fce  jmp     short loc_1800B9F8A
0x1800b9fd0  mov     dword ptr [rsp+310h+var_2E8], 4
0x1800b9fd8  lea     r9, [rsp+310h+var_2B8]
0x1800b9fdd  xor     r8d, r8d
0x1800b9fe0  mov     dword ptr [rsp+310h+var_2F0], 1000h
0x1800b9fe8  lea     rdx, [rsp+310h+var_2A8]
0x1800b9fed  mov     [rsp+310h+var_2B8], 1
0x1800b9ff6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800b9ffa  mov     [rsp+310h+var_2A8], 0
0x1800ba003  call    ZwAllocateVirtualMemory
0x1800ba008  mov     esi, eax
0x1800ba00a  test    eax, eax
0x1800ba00c  js      loc_1800BA121
0x1800ba012  test    rbx, rbx
0x1800ba015  jnz     short loc_1800BA07F
0x1800ba017  mov     rdi, [rsp+310h+var_2A8]
0x1800ba01c  mov     rbx, rdi
0x1800ba01f  mov     rax, [rsp+310h+var_2B8]
0x1800ba024  add     rax, 0FFFFFFFFFFFFFFF0h
0x1800ba028  shr     rax, 2
0x1800ba02c  mov     [rdi+8], ax
0x1800ba030  xor     eax, eax
0x1800ba032  mov     [rdi+0Ah], ax
0x1800ba036  jmp     loc_1800B9E63
0x1800ba03b  test    edi, edi
0x1800ba03d  js      short loc_1800BA08E
0x1800ba03f  mov     rsi, [rsi]
0x1800ba042  jmp     loc_1800B9F7E
0x1800ba047  mov     rcx, rbx
0x1800ba04a  call    PsspFreeLinkedHandleList
0x1800ba04f  mov     eax, 0C0000095h
0x1800ba054  mov     rcx, [rbp+210h+var_40]
0x1800ba05b  xor     rcx, rsp; StackCookie
0x1800ba05e  call    __security_check_cookie
0x1800ba063  mov     rbx, [rsp+310h+arg_10]
0x1800ba06b  add     rsp, 2E0h
0x1800ba072  pop     r15
0x1800ba074  pop     r14
0x1800ba076  pop     r13
0x1800ba078  pop     r12
0x1800ba07a  pop     rdi
0x1800ba07b  pop     rsi
0x1800ba07c  pop     rbp
0x1800ba07d  retn
0x1800ba07f  mov     rax, [rsp+310h+var_2A8]
0x1800ba084  mov     [rdi], rax
0x1800ba087  mov     rdi, [rsp+310h+var_2A8]
0x1800ba08c  jmp     short loc_1800BA01F
0x1800ba08e  mov     rdx, [rsp+310h+var_2A0]
0x1800ba093  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800ba097  call    NtUnmapViewOfSection
0x1800ba09c  mov     rcx, rbx
0x1800ba09f  call    PsspFreeLinkedHandleList
0x1800ba0a4  mov     eax, dword ptr [rbp+210h+var_268]
0x1800ba0a7  mov     [r13+3E0h], eax
0x1800ba0ae  mov     eax, dword ptr [rbp+210h+var_278+0Ch]
0x1800ba0b1  mov     [r13+3E8h], rax
0x1800ba0b8  mov     rax, [rsp+310h+Handle]
0x1800ba0bd  mov     [r13+3F0h], rax
0x1800ba0c4  mov     eax, 7FFE0014h
0x1800ba0c9  mov     rax, [rax]
0x1800ba0cc  mov     [r13+3F8h], rax
0x1800ba0d3  xor     eax, eax
0x1800ba0d5  jmp     loc_1800BA054
0x1800ba0da  mov     ecx, [rsp+310h+var_2B0]
0x1800ba0de  lea     rdx, [rsp+310h+var_2C0]
0x1800ba0e3  call    RtlGetExtendedContextLength
0x1800ba0e8  mov     r14d, [rsp+310h+var_2C0]
0x1800ba0ed  test    eax, eax
0x1800ba0ef  jns     loc_1800B9EAE
0x1800ba0f5  jmp     loc_1800B9EA8
0x1800ba0fa  mov     rdx, [rsp+310h+var_2A0]
0x1800ba0ff  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800ba103  call    NtUnmapViewOfSection
0x1800ba108  mov     rcx, [rsp+310h+Handle]; Handle
0x1800ba10d  call    NtClose
0x1800ba112  mov     rcx, rbx
0x1800ba115  call    PsspFreeLinkedHandleList
0x1800ba11a  mov     eax, edi
0x1800ba11c  jmp     loc_1800BA054
0x1800ba121  mov     rcx, rbx
0x1800ba124  call    PsspFreeLinkedHandleList
0x1800ba129  mov     eax, esi
0x1800ba12b  jmp     loc_1800BA054
```
