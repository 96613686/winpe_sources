# Smb2QueryInformation

- ea: `0x140016320`
- end: `0x140016501`
- name: `Smb2QueryInformation`
- size: `481`
- prototype: `__int64 __fastcall(__int64, int, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14002d8e0`

## callees

- `0x140016320`
- `0x1400372c0`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x1400164a9`
- `ntoskrnl!RtlLengthSid` at `0x1400164a9`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140016439`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14001647c`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140016439`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14001647c`
- `mrxsmb!SmbCeInitiateExchange` at `0x140016414`
- `mrxsmb!SmbCeInitiateExchange` at `0x140016414`
- `mrxsmb!SmbCeInitializeExchange` at `0x140016397`
- `mrxsmb!SmbCeInitializeExchange` at `0x140016397`

## pseudocode

```c
__int64 __fastcall Smb2QueryInformation(__int64 a1, int a2, int a3, int a4)
{
  __int64 v4; // rax
  ULONG v9; // r12d
  __int64 v10; // r14
  int v11; // eax
  __int64 result; // rax
  unsigned int v13; // ebx
  int v14; // ebx
  int v15; // ecx
  void *v16; // rcx
  ULONG v17; // eax
  __int64 v18; // rdx
  int v19; // ecx
  __int64 v20; // [rsp+90h] [rbp+8h] BYREF

  v4 = *(_QWORD *)(a1 + 72);
  v20 = 0;
  v9 = 0;
  v10 = *(_QWORD *)(*(_QWORD *)(v4 + 40) + 40LL);
  if ( a2 == 4 )
  {
    if ( *(_QWORD *)(a1 + 528) || (v16 = *(void **)(a1 + 520)) == 0 )
    {
      v17 = *(_DWORD *)(a1 + 536);
    }
    else
    {
      v17 = RtlLengthSid(v16);
      v9 = v17;
    }
    v11 = v17 + 2616;
  }
  else
  {
    v11 = 2600;
  }
  v20 = 0;
  result = SmbCeInitializeExchange(&v20, a1, 0, 0, 0, v10, v11, &QueryInfoDispatch);
  if ( !(_DWORD)result )
  {
    *(_DWORD *)(v20 + 2424) = a3;
    *(_DWORD *)(v20 + 2420) = a2;
    *(_QWORD *)(v20 + 2408) = *(_QWORD *)(a1 + 456);
    *(_DWORD *)(v20 + 2416) = *(_DWORD *)(a1 + 472);
    if ( a2 == 1 )
    {
      if ( a3 != 15 )
        goto LABEL_6;
      *(_DWORD *)(v20 + 2428) = a4;
      *(_QWORD *)(v20 + 2440) = *(_QWORD *)(a1 + 512);
      *(_DWORD *)(v20 + 2448) = *(_DWORD *)(a1 + 520);
      v15 = *(_DWORD *)(a1 + 524);
    }
    else
    {
      v14 = a2 - 3;
      if ( v14 )
      {
        if ( v14 == 1 )
        {
          v18 = v20 + 2592;
          *(_QWORD *)(v20 + 2440) = v20 + 2592;
          *(_BYTE *)(v18 + 1) = *(_BYTE *)(a1 + 540);
          *(_BYTE *)v18 = *(_BYTE *)(a1 + 541);
          *(_DWORD *)(v18 + 4) = *(_DWORD *)(a1 + 536);
          *(_DWORD *)(v18 + 12) = 0;
          *(_DWORD *)(v18 + 8) = v9;
          *(_DWORD *)(v20 + 2448) = 16;
          v19 = *(_DWORD *)(a1 + 536);
          if ( v19 && *(_QWORD *)(a1 + 528) )
          {
            *(_DWORD *)(v20 + 2448) = v19 + 16;
            memmove(
              (void *)(v18 + 16 + *(unsigned int *)(v18 + 12)),
              *(const void **)(a1 + 528),
              *(unsigned int *)(v18 + 4));
          }
          else if ( *(_QWORD *)(a1 + 520) )
          {
            *(_DWORD *)(v20 + 2448) = *(_DWORD *)(v18 + 8) + 16;
            memmove((void *)(v18 + 16 + *(unsigned int *)(v18 + 12)), *(const void **)(a1 + 520), v9);
          }
        }
        goto LABEL_6;
      }
      v15 = *(_DWORD *)(a1 + 512);
    }
    *(_DWORD *)(v20 + 2432) = v15;
LABEL_6:
    _InterlockedOr((volatile signed __int32 *)(v20 + 68), 1u);
    v13 = SmbCeInitiateExchange(v20);
    if ( v13 == 259 )
    {
      return SmbCeWaitForCompletionAndFinalizeExchangeEx(v20, 0, 0, 0);
    }
    else
    {
      SmbCeWaitForCompletionAndFinalizeExchangeEx(v20, 0, 0, 0);
      return v13;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140016320  push    rbx
0x140016322  push    rbp
0x140016323  push    rsi
0x140016324  push    rdi
0x140016325  push    r12
0x140016327  push    r13
0x140016329  push    r14
0x14001632b  push    r15
0x14001632d  sub     rsp, 48h
0x140016331  mov     rax, [rcx+48h]
0x140016335  xor     r13d, r13d
0x140016338  mov     ebx, edx
0x14001633a  mov     [rsp+88h+arg_0], r13
0x140016342  mov     r15d, r9d
0x140016345  mov     ebp, r8d
0x140016348  mov     rdi, rcx
0x14001634b  mov     r12d, r13d
0x14001634e  mov     rdx, [rax+28h]
0x140016352  mov     r14, [rdx+28h]
0x140016356  cmp     ebx, 4
0x140016359  jz      loc_14001648C
0x14001635f  mov     eax, 0A28h
0x140016364  lea     rcx, QueryInfoDispatch
0x14001636b  mov     [rsp+88h+arg_0], r13
0x140016373  mov     [rsp+88h+var_50], rcx
0x140016378  xor     r9d, r9d
0x14001637b  mov     [rsp+88h+var_58], eax
0x14001637f  lea     rcx, [rsp+88h+arg_0]
0x140016387  mov     [rsp+88h+var_60], r14
0x14001638c  xor     r8d, r8d
0x14001638f  mov     rdx, rdi
0x140016392  mov     [rsp+88h+var_68], r13
0x140016397  call    cs:__imp_SmbCeInitializeExchange
0x14001639e  nop     dword ptr [rax+rax+00h]
0x1400163a3  test    eax, eax
0x1400163a5  jnz     loc_140016445
0x1400163ab  mov     rax, [rsp+88h+arg_0]
0x1400163b3  mov     [rax+978h], ebp
0x1400163b9  mov     rax, [rsp+88h+arg_0]
0x1400163c1  mov     [rax+974h], ebx
0x1400163c7  mov     rax, [rsp+88h+arg_0]
0x1400163cf  mov     rcx, [rdi+1C8h]
0x1400163d6  mov     [rax+968h], rcx
0x1400163dd  mov     rax, [rsp+88h+arg_0]
0x1400163e5  mov     ecx, [rdi+1D8h]
0x1400163eb  mov     [rax+970h], ecx
0x1400163f1  cmp     ebx, 1
0x1400163f4  jnz     short loc_140016457
0x1400163f6  cmp     ebp, 0Fh
0x1400163f9  jz      loc_1400164BD
0x1400163ff  mov     rax, [rsp+88h+arg_0]
0x140016407  lock or dword ptr [rax+44h], 1
0x14001640c  mov     rcx, [rsp+88h+arg_0]
0x140016414  call    cs:__imp_SmbCeInitiateExchange
0x14001641b  nop     dword ptr [rax+rax+00h]
0x140016420  mov     rcx, [rsp+88h+arg_0]
0x140016428  xor     r9d, r9d
0x14001642b  xor     r8d, r8d
0x14001642e  xor     edx, edx
0x140016430  mov     ebx, eax
0x140016432  cmp     eax, 103h
0x140016437  jnz     short loc_14001647C
0x140016439  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x140016440  nop     dword ptr [rax+rax+00h]
0x140016445  add     rsp, 48h
0x140016449  pop     r15
0x14001644b  pop     r14
0x14001644d  pop     r13
0x14001644f  pop     r12
0x140016451  pop     rdi
0x140016452  pop     rsi
0x140016453  pop     rbp
0x140016454  pop     rbx
0x140016455  retn
0x140016457  sub     ebx, 3
0x14001645a  jz      short loc_140016466
0x14001645c  cmp     ebx, 1
0x14001645f  jnz     short loc_1400163FF
0x140016461  jmp     loc_14003B59C
0x140016466  mov     ecx, [rdi+200h]
0x14001646c  mov     rax, [rsp+88h+arg_0]
0x140016474  mov     [rax+980h], ecx
0x14001647a  jmp     short loc_1400163FF
0x14001647c  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x140016483  nop     dword ptr [rax+rax+00h]
0x140016488  mov     eax, ebx
0x14001648a  jmp     short loc_140016445
0x14001648c  cmp     [rcx+210h], r12
0x140016493  jnz     loc_14003B58C
0x140016499  mov     rcx, [rcx+208h]; Sid
0x1400164a0  test    rcx, rcx
0x1400164a3  jz      loc_14003B58C
0x1400164a9  call    cs:__imp_RtlLengthSid
0x1400164b0  nop     dword ptr [rax+rax+00h]
0x1400164b5  mov     r12d, eax
0x1400164b8  jmp     loc_14003B592
0x1400164bd  mov     rax, [rsp+88h+arg_0]
0x1400164c5  mov     [rax+97Ch], r15d
0x1400164cc  mov     rax, [rsp+88h+arg_0]
0x1400164d4  mov     rcx, [rdi+200h]
0x1400164db  mov     [rax+988h], rcx
0x1400164e2  mov     ecx, [rdi+208h]
0x1400164e8  mov     rax, [rsp+88h+arg_0]
0x1400164f0  mov     [rax+990h], ecx
0x1400164f6  mov     ecx, [rdi+20Ch]
0x1400164fc  jmp     loc_14001646C
0x14003b58c  mov     eax, [rdi+218h]
0x14003b592  add     eax, 0A38h
0x14003b597  jmp     loc_140016364
0x14003b59c  mov     rax, [rsp+88h+arg_0]
0x14003b5a4  lea     rdx, [rax+0A20h]
0x14003b5ab  mov     [rax+988h], rdx
0x14003b5b2  movzx   eax, byte ptr [rdi+21Ch]
0x14003b5b9  mov     [rdx+1], al
0x14003b5bc  movzx   eax, byte ptr [rdi+21Dh]
0x14003b5c3  mov     [rdx], al
0x14003b5c5  mov     eax, [rdi+218h]
0x14003b5cb  mov     [rdx+4], eax
0x14003b5ce  mov     [rdx+0Ch], r13d
0x14003b5d2  mov     [rdx+8], r12d
0x14003b5d6  mov     rax, [rsp+88h+arg_0]
0x14003b5de  mov     dword ptr [rax+990h], 10h
0x14003b5e8  mov     ecx, [rdi+218h]
0x14003b5ee  test    ecx, ecx
0x14003b5f0  jz      short loc_14003B62C
0x14003b5f2  cmp     [rdi+210h], r13
0x14003b5f9  jz      short loc_14003B62C
0x14003b5fb  mov     rax, [rsp+88h+arg_0]
0x14003b603  add     ecx, 10h
0x14003b606  mov     [rax+990h], ecx
0x14003b60c  mov     ecx, [rdx+0Ch]
0x14003b60f  mov     r8d, [rdx+4]; Size
0x14003b613  add     rdx, 10h
0x14003b617  add     rcx, rdx; void *
0x14003b61a  mov     rdx, [rdi+210h]; Src
0x14003b621  call    memmove
0x14003b626  nop
0x14003b627  jmp     loc_1400163FF
0x14003b62c  cmp     [rdi+208h], r13
0x14003b633  jz      loc_1400163FF
0x14003b639  mov     ecx, [rdx+8]
0x14003b63c  mov     rax, [rsp+88h+arg_0]
0x14003b644  add     ecx, 10h
0x14003b647  mov     r8d, r12d; Size
0x14003b64a  mov     [rax+990h], ecx
0x14003b650  mov     ecx, [rdx+0Ch]
0x14003b653  add     rdx, 10h
0x14003b657  add     rcx, rdx; void *
0x14003b65a  mov     rdx, [rdi+208h]; Src
0x14003b661  call    memmove
0x14003b666  nop
0x14003b667  jmp     loc_1400163FF
```
