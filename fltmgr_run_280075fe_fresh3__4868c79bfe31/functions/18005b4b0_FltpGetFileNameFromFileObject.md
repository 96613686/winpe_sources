# FltpGetFileNameFromFileObject

- ea: `0x18005b4b0`
- end: `0x18005b877`
- name: `FltpGetFileNameFromFileObject`
- size: `967`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18005a2e0`

## callees

- `0x180009f20`
- `0x18000dcb0`
- `0x18000e2e0`
- `0x18000eb80`
- `0x180058380`
- `0x18005b4b0`
- `0x1800629c0`
- `0x18006e9a0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x18005b54b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18005b6f1`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800794a7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18005b54b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18005b6f1`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800794a7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005b57d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005b72f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005b57d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005b72f`

## pseudocode

```c
__int64 __fastcall FltpGetFileNameFromFileObject(__int64 a1)
{
  __int64 v1; // rdx
  PFLT_INSTANCE *v2; // rbp
  struct _FILE_OBJECT *v4; // r8
  int v5; // r8d
  __int64 v6; // rax
  const UNICODE_STRING **v7; // rdi
  int **v8; // r15
  unsigned __int16 *v9; // rax
  unsigned int v10; // edx
  PUNICODE_STRING v11; // r10
  PUNICODE_STRING *v12; // rsi
  const UNICODE_STRING *v13; // rdx
  __int64 v14; // rcx
  unsigned __int16 v15; // r8
  const UNICODE_STRING *v16; // rdx
  int FileNameInformation; // r14d
  int v18; // ecx
  int v20; // eax
  unsigned int v21; // r8d
  __int64 v22; // rcx
  __int64 v23; // rax
  __int16 v24; // cx
  struct _FLT_FILE_NAME_INFORMATION *v25; // rcx
  wchar_t *Buffer; // rax
  unsigned __int64 v27; // rcx
  const UNICODE_STRING *v28; // rdx
  const UNICODE_STRING *v29; // rdx
  __int64 v30; // rcx
  const UNICODE_STRING *v31; // rdx
  unsigned __int16 *p_Length; // rcx
  unsigned __int16 *v33; // rax
  __int64 v34; // [rsp+48h] [rbp-60h]
  __int128 v35; // [rsp+60h] [rbp-48h] BYREF
  PFLT_INSTANCE *v36; // [rsp+B0h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 64);
  v2 = 0;
  v36 = 0;
  v4 = *(struct _FILE_OBJECT **)(v1 + 64);
  if ( v4 )
  {
    if ( v4->FsContext )
    {
      if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 16LL) + 4LL) != 1 || *(_WORD *)(v1 + 88) )
      {
        FileNameInformation = FltpAllocateInitializeNameGenerationContext(
                                &v36,
                                0,
                                v4,
                                0,
                                258,
                                0,
                                0,
                                0,
                                0,
                                v34,
                                *(_DWORD *)(a1 + 40) & 0x400 | 1u);
        v20 = FltpDbgStatus(
                (unsigned int)FileNameInformation,
                "minkernel\\fs\\filtermgr\\filter\\namesup.c",
                2377,
                3221225626LL);
        v2 = v36;
        if ( v20 >= 0 )
        {
          FileNameInformation = FltpGetFileNameInformation(v36);
          if ( FileNameInformation >= 0 )
          {
            v21 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 64) + 88LL) + LOWORD(v2[15]->Base.RundownRef.Count) + 2;
            if ( v21 > 0xFFFE )
            {
              FileNameInformation = -1073741562;
            }
            else
            {
              v22 = *(_QWORD *)(a1 + 112);
              v12 = (PUNICODE_STRING *)(a1 + 112);
              if ( v21 <= (unsigned __int64)*(unsigned int *)(v22 + 20) - 2
                || (FileNameInformation = FltpReallocNameControl((unsigned __int16 *)v22, v21 + 514, 0, 0),
                    FileNameInformation >= 0) )
              {
                RtlCopyUnicodeString(*v12, (PCUNICODE_STRING)&v2[15]->Base.RundownRef);
                LOWORD((*v12)[1].Buffer) = v2[15]->Base.UniqueIdentifier.Data1;
                v23 = *(_QWORD *)(a1 + 64);
                if ( *(_WORD *)(v23 + 88) )
                {
                  v24 = **(_WORD **)(v23 + 96);
                  if ( v24 != 92 && v24 != 58 )
                  {
                    Buffer = (*v12)->Buffer;
                    v27 = (unsigned __int64)(*v12)->Length >> 1;
                    if ( Buffer[v27 - 1] != 92 )
                    {
                      Buffer[v27] = 92;
                      (*v12)->Length += 2;
                    }
                  }
                }
                FileNameInformation = RtlAppendUnicodeStringToString(
                                        *v12,
                                        (PCUNICODE_STRING)(*(_QWORD *)(a1 + 64) + 88LL));
                v7 = (const UNICODE_STRING **)(a1 + 24);
                v8 = (int **)(a1 + 32);
                goto LABEL_15;
              }
            }
          }
        }
LABEL_16:
        if ( v2 )
        {
          v25 = (struct _FLT_FILE_NAME_INFORMATION *)v2[15];
          if ( v25 )
            FltReleaseFileNameInformation(v25);
          FltpFreeNameGenerationContext(v2);
        }
        return (unsigned int)FileNameInformation;
      }
      v28 = *(const UNICODE_STRING **)(a1 + 24);
      v7 = (const UNICODE_STRING **)(a1 + 24);
      v8 = (int **)(a1 + 32);
      if ( v28 )
        v29 = v28 + 7;
      else
        v29 = (const UNICODE_STRING *)(*v8 + 2);
      v12 = (PUNICODE_STRING *)(a1 + 112);
      RtlCopyUnicodeString(*(PUNICODE_STRING *)(a1 + 112), v29);
      FileNameInformation = 0;
LABEL_15:
      if ( (*(_DWORD *)(*(_QWORD *)(a1 + 64) + 80LL) & 0x400000) != 0 )
      {
        v31 = *v7;
        *(_DWORD *)(a1 + 40) |= 4u;
        p_Length = &v31[7].Length;
        v33 = v31 ? (unsigned __int16 *)&v31[7] : (unsigned __int16 *)(*v8 + 2);
        if ( (*v12)->Length > *v33 )
        {
          if ( !v31 )
            p_Length = (unsigned __int16 *)(*v8 + 2);
          (*v12)->Length = *p_Length;
        }
      }
      goto LABEL_16;
    }
    return 3221225485LL;
  }
  else
  {
    v35 = 0;
    v5 = *(unsigned __int16 *)(v1 + 88);
    if ( v5 != 1 )
    {
      v6 = *(_QWORD *)(a1 + 24);
      v7 = (const UNICODE_STRING **)(a1 + 24);
      v8 = (int **)(a1 + 32);
      if ( v6 )
        v9 = (unsigned __int16 *)(v6 + 112);
      else
        v9 = (unsigned __int16 *)(*v8 + 2);
      v10 = v5 + *v9;
      if ( v10 > 0xFFFE )
      {
        return (unsigned int)-1073741562;
      }
      else
      {
        v11 = *(PUNICODE_STRING *)(a1 + 112);
        v12 = (PUNICODE_STRING *)(a1 + 112);
        if ( v10 <= (unsigned __int64)*(unsigned int *)(&v11[1].MaximumLength + 1) - 2 )
        {
LABEL_7:
          if ( *v7 )
            v13 = *v7 + 7;
          else
            v13 = (const UNICODE_STRING *)(*v8 + 2);
          RtlCopyUnicodeString(v11, v13);
          v14 = *(_QWORD *)(a1 + 64);
          v15 = *(_WORD *)(v14 + 88);
          v16 = (const UNICODE_STRING *)(v14 + 88);
          if ( v15 >= 4u && *(_WORD *)(*(_QWORD *)(v14 + 96) + 2LL) == 92 )
          {
            v16 = (const UNICODE_STRING *)&v35;
            WORD1(v35) = v15 - 2;
            LOWORD(v35) = v15 - 2;
            *((_QWORD *)&v35 + 1) = *(_QWORD *)(v14 + 96) + 2LL;
          }
          FileNameInformation = RtlAppendUnicodeStringToString(*v12, v16);
          if ( *v7 )
            v18 = (int)(*v7)[3].Buffer;
          else
            v18 = **v8;
          if ( (v18 & 1) != 0 )
          {
            if ( *v7 )
              v30 = (__int64)&(*v7)[7];
            else
              v30 = (__int64)(*v8 + 2);
            FltpParseShareName(v30, *v12);
          }
          goto LABEL_15;
        }
        FileNameInformation = FltpReallocNameControl(&v11->Length, v10 + 514, 0, 0);
        if ( FileNameInformation >= 0 )
        {
          v11 = *v12;
          v8 = (int **)(a1 + 32);
          goto LABEL_7;
        }
      }
      return (unsigned int)FileNameInformation;
    }
    return 3223060485LL;
  }
}

```

## disassembly

```asm
0x18005b4b0  push    rbx
0x18005b4b2  push    rbp
0x18005b4b3  push    rsi
0x18005b4b4  push    rdi
0x18005b4b5  push    r14
0x18005b4b7  push    r15
0x18005b4b9  sub     rsp, 78h
0x18005b4bd  mov     rdx, [rcx+40h]
0x18005b4c1  xor     ebp, ebp
0x18005b4c3  mov     rbx, rcx
0x18005b4c6  mov     [rsp+0A8h+arg_0], rbp
0x18005b4ce  mov     r8, [rdx+40h]
0x18005b4d2  test    r8, r8
0x18005b4d5  jnz     loc_18005B609
0x18005b4db  xorps   xmm0, xmm0
0x18005b4de  movups  [rsp+0A8h+var_48], xmm0
0x18005b4e3  movzx   r8d, word ptr [rdx+58h]
0x18005b4e8  cmp     r8d, 1
0x18005b4ec  jz      loc_18005B5CF
0x18005b4f2  mov     rax, [rcx+18h]
0x18005b4f6  lea     rdi, [rcx+18h]
0x18005b4fa  lea     r15, [rcx+20h]
0x18005b4fe  test    rax, rax
0x18005b501  jz      loc_18005B7F1
0x18005b507  add     rax, 70h ; 'p'
0x18005b50b  movzx   edx, word ptr [rax]
0x18005b50e  add     edx, r8d
0x18005b511  cmp     edx, 0FFFEh
0x18005b517  ja      loc_18005B7FD
0x18005b51d  mov     r10, [rcx+70h]
0x18005b521  lea     rsi, [rcx+70h]
0x18005b525  mov     eax, edx
0x18005b527  mov     ecx, [r10+14h]
0x18005b52b  sub     rcx, 2
0x18005b52f  cmp     rax, rcx
0x18005b532  ja      loc_18005B5E2
0x18005b538  mov     rax, [rdi]
0x18005b53b  test    rax, rax
0x18005b53e  jz      loc_18005B808
0x18005b544  lea     rdx, [rax+70h]; SourceString
0x18005b548  mov     rcx, r10; DestinationString
0x18005b54b  call    cs:__imp_RtlCopyUnicodeString
0x18005b552  nop     dword ptr [rax+rax+00h]
0x18005b557  mov     rcx, [rbx+40h]
0x18005b55b  movzx   r8d, word ptr [rcx+58h]
0x18005b560  lea     rdx, [rcx+58h]; Source
0x18005b564  cmp     r8w, 4
0x18005b569  jb      short loc_18005B57A
0x18005b56b  mov     rax, [rcx+60h]
0x18005b56f  cmp     word ptr [rax+2], 5Ch ; '\'
0x18005b574  jz      loc_18005B814
0x18005b57a  mov     rcx, [rsi]; Destination
0x18005b57d  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005b584  nop     dword ptr [rax+rax+00h]
0x18005b589  mov     r14d, eax
0x18005b58c  mov     rax, [rdi]
0x18005b58f  test    rax, rax
0x18005b592  jz      loc_18005B83C
0x18005b598  mov     ecx, [rax+38h]
0x18005b59b  test    cl, 1
0x18005b59e  jnz     loc_18005B846
0x18005b5a4  mov     rax, [rbx+40h]
0x18005b5a8  mov     ecx, [rax+50h]
0x18005b5ab  bt      ecx, 16h
0x18005b5af  jb      loc_18005B85B
0x18005b5b5  test    rbp, rbp
0x18005b5b8  jnz     loc_18005B74B
0x18005b5be  mov     eax, r14d
0x18005b5c1  add     rsp, 78h
0x18005b5c5  pop     r15
0x18005b5c7  pop     r14
0x18005b5c9  pop     rdi
0x18005b5ca  pop     rsi
0x18005b5cb  pop     rbp
0x18005b5cc  pop     rbx
0x18005b5cd  retn
0x18005b5cf  mov     eax, 0C01C0005h
0x18005b5d4  add     rsp, 78h
0x18005b5d8  pop     r15
0x18005b5da  pop     r14
0x18005b5dc  pop     rdi
0x18005b5dd  pop     rsi
0x18005b5de  pop     rbp
0x18005b5df  pop     rbx
0x18005b5e0  retn
0x18005b5e2  add     edx, 202h
0x18005b5e8  xor     r9d, r9d
0x18005b5eb  xor     r8d, r8d
0x18005b5ee  mov     rcx, r10
0x18005b5f1  call    FltpReallocNameControl
0x18005b5f6  mov     r14d, eax
0x18005b5f9  test    eax, eax
0x18005b5fb  js      short loc_18005B5BE
0x18005b5fd  mov     r10, [rsi]
0x18005b600  lea     r15, [rbx+20h]
0x18005b604  jmp     loc_18005B538
0x18005b609  cmp     [r8+18h], rbp
0x18005b60d  jz      loc_18005B7B4
0x18005b613  mov     rax, [rcx+50h]
0x18005b617  mov     rcx, [rax+10h]
0x18005b61b  cmp     byte ptr [rcx+4], 1
0x18005b61f  jz      loc_18005B7BE
0x18005b625  mov     eax, [rbx+28h]
0x18005b628  lea     rcx, [rsp+0A8h+arg_0]
0x18005b630  and     eax, 400h
0x18005b635  xor     r9d, r9d
0x18005b638  or      eax, 1
0x18005b63b  xor     edx, edx
0x18005b63d  mov     [rsp+0A8h+var_58], eax
0x18005b641  mov     [rsp+0A8h+var_68], ebp
0x18005b645  mov     [rsp+0A8h+var_70], rbp
0x18005b64a  mov     [rsp+0A8h+var_78], rbp
0x18005b64f  mov     [rsp+0A8h+var_80], rbp
0x18005b654  mov     dword ptr [rsp+0A8h+var_88], 102h
0x18005b65c  call    FltpAllocateInitializeNameGenerationContext
0x18005b661  mov     r8d, 949h
0x18005b667  mov     [rsp+0A8h+var_88], rbp
0x18005b66c  mov     r9d, 0C000009Ah
0x18005b672  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005b679  mov     ecx, eax
0x18005b67b  mov     r14d, eax
0x18005b67e  call    FltpDbgStatus
0x18005b683  mov     rbp, [rsp+0A8h+arg_0]
0x18005b68b  test    eax, eax
0x18005b68d  js      loc_18005B5B5
0x18005b693  mov     rcx, rbp
0x18005b696  call    FltpGetFileNameInformation
0x18005b69b  mov     r14d, eax
0x18005b69e  test    eax, eax
0x18005b6a0  js      loc_18005B5B5
0x18005b6a6  mov     rax, [rbx+40h]
0x18005b6aa  movzx   edx, word ptr [rax+58h]
0x18005b6ae  mov     rax, [rbp+78h]
0x18005b6b2  movzx   r8d, word ptr [rax+8]
0x18005b6b7  add     r8d, 2
0x18005b6bb  add     r8d, edx
0x18005b6be  cmp     r8d, 0FFFEh
0x18005b6c5  ja      loc_18005B7E6
0x18005b6cb  mov     rcx, [rbx+70h]
0x18005b6cf  lea     rsi, [rbx+70h]
0x18005b6d3  mov     eax, r8d
0x18005b6d6  mov     edx, [rcx+14h]
0x18005b6d9  sub     rdx, 2
0x18005b6dd  cmp     rax, rdx
0x18005b6e0  ja      loc_18005B792
0x18005b6e6  mov     rdx, [rbp+78h]
0x18005b6ea  mov     rcx, [rsi]; DestinationString
0x18005b6ed  add     rdx, 8; SourceString
0x18005b6f1  call    cs:__imp_RtlCopyUnicodeString
0x18005b6f8  nop     dword ptr [rax+rax+00h]
0x18005b6fd  mov     rax, [rbp+78h]
0x18005b701  mov     rcx, [rsi]
0x18005b704  movzx   eax, word ptr [rax+28h]
0x18005b708  mov     [rcx+18h], ax
0x18005b70c  mov     rax, [rbx+40h]
0x18005b710  cmp     word ptr [rax+58h], 0
0x18005b715  jbe     short loc_18005B724
0x18005b717  mov     rax, [rax+60h]
0x18005b71b  movzx   ecx, word ptr [rax]
0x18005b71e  cmp     cx, 5Ch ; '\'
0x18005b722  jnz     short loc_18005B761
0x18005b724  mov     rdx, [rbx+40h]
0x18005b728  mov     rcx, [rsi]; Destination
0x18005b72b  add     rdx, 58h ; 'X'; Source
0x18005b72f  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005b736  nop     dword ptr [rax+rax+00h]
0x18005b73b  mov     r14d, eax
0x18005b73e  lea     rdi, [rbx+18h]
0x18005b742  lea     r15, [rbx+20h]
0x18005b746  jmp     loc_18005B5A4
0x18005b74b  mov     rcx, [rbp+78h]; FileNameInformation
0x18005b74f  test    rcx, rcx
0x18005b752  jnz     short loc_18005B78B
0x18005b754  mov     rcx, rbp; Entry
0x18005b757  call    FltpFreeNameGenerationContext
0x18005b75c  jmp     loc_18005B5BE
0x18005b761  cmp     cx, 3Ah ; ':'
0x18005b765  jz      short loc_18005B724
0x18005b767  mov     rax, [rsi]
0x18005b76a  movzx   ecx, word ptr [rax]
0x18005b76d  mov     rax, [rax+8]
0x18005b771  shr     rcx, 1
0x18005b774  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x18005b77a  jz      short loc_18005B724
0x18005b77c  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x18005b782  mov     rax, [rsi]
0x18005b785  add     word ptr [rax], 2
0x18005b789  jmp     short loc_18005B724
0x18005b78b  call    FltReleaseFileNameInformation
0x18005b790  jmp     short loc_18005B754
0x18005b792  lea     edx, [r8+202h]
0x18005b799  xor     r9d, r9d
0x18005b79c  xor     r8d, r8d
0x18005b79f  call    FltpReallocNameControl
0x18005b7a4  mov     r14d, eax
0x18005b7a7  test    eax, eax
0x18005b7a9  jns     loc_18005B6E6
0x18005b7af  jmp     loc_18005B5B5
0x18005b7b4  mov     eax, 0C000000Dh
0x18005b7b9  jmp     loc_18005B5C1
0x18005b7be  cmp     [rdx+58h], bp
0x18005b7c2  jnz     loc_18005B625
0x18005b7c8  mov     rdx, [rbx+18h]
0x18005b7cc  lea     rdi, [rbx+18h]
0x18005b7d0  lea     r15, [rbx+20h]
0x18005b7d4  test    rdx, rdx
0x18005b7d7  jz      loc_180079498
0x18005b7dd  add     rdx, 70h ; 'p'
0x18005b7e1  jmp     loc_18007949F
0x18005b7e6  mov     r14d, 0C0000106h
0x18005b7ec  jmp     loc_18005B5B5
0x18005b7f1  mov     rax, [r15]
0x18005b7f4  add     rax, 8
0x18005b7f8  jmp     loc_18005B50B
0x18005b7fd  mov     r14d, 0C0000106h
0x18005b803  jmp     loc_18005B5BE
0x18005b808  mov     rdx, [r15]
0x18005b80b  add     rdx, 8
0x18005b80f  jmp     loc_18005B548
0x18005b814  sub     r8w, 2
0x18005b819  lea     rdx, [rsp+0A8h+var_48]
0x18005b81e  mov     word ptr [rsp+0A8h+var_48+2], r8w
0x18005b824  mov     word ptr [rsp+0A8h+var_48], r8w
0x18005b82a  mov     rax, [rcx+60h]
0x18005b82e  add     rax, 2
0x18005b832  mov     qword ptr [rsp+0A8h+var_48+8], rax
0x18005b837  jmp     loc_18005B57A
0x18005b83c  mov     rax, [r15]
0x18005b83f  mov     ecx, [rax]
0x18005b841  jmp     loc_18005B59B
0x18005b846  mov     rcx, [rdi]
0x18005b849  test    rcx, rcx
0x18005b84c  jz      loc_1800794BB
0x18005b852  add     rcx, 70h ; 'p'
0x18005b856  jmp     loc_1800794C2
0x18005b85b  mov     rdx, [rdi]
0x18005b85e  or      dword ptr [rbx+28h], 4
0x18005b862  lea     rcx, [rdx+70h]
0x18005b866  test    rdx, rdx
0x18005b869  jz      loc_1800794D0
0x18005b86f  mov     rax, rcx
0x18005b872  jmp     loc_1800794D7
0x180079498  mov     rdx, [r15]
0x18007949b  add     rdx, 8; SourceString
0x18007949f  mov     rcx, [rbx+70h]; DestinationString
0x1800794a3  lea     rsi, [rbx+70h]
0x1800794a7  call    cs:__imp_RtlCopyUnicodeString
0x1800794ae  nop     dword ptr [rax+rax+00h]
0x1800794b3  xor     r14d, r14d
0x1800794b6  jmp     loc_18005B5A4
0x1800794bb  mov     rcx, [r15]
0x1800794be  add     rcx, 8
0x1800794c2  mov     rdx, [rsi]
0x1800794c5  call    FltpParseShareName
0x1800794ca  nop
0x1800794cb  jmp     loc_18005B5A4
0x1800794d0  mov     rax, [r15]
0x1800794d3  add     rax, 8
0x1800794d7  mov     r8, [rsi]
0x1800794da  movzx   eax, word ptr [rax]
0x1800794dd  cmp     [r8], ax
0x1800794e1  jbe     loc_18005B5B5
0x1800794e7  test    rdx, rdx
0x1800794ea  jnz     short loc_1800794F3
0x1800794ec  mov     rcx, [r15]
0x1800794ef  add     rcx, 8
0x1800794f3  movzx   eax, word ptr [rcx]
0x1800794f6  mov     [r8], ax
0x1800794fa  jmp     loc_18005B5B5
```
