# CscPqEnumContinue

- ea: `0x140060ac0`
- end: `0x140060c9f`
- name: `CscPqEnumContinue`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14005837c`

## callees

- `0x1400063f0`
- `0x140016a04`
- `0x1400190ec`
- `0x140060ac0`
- `0x14008c8a4`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140060b1d`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140060b1d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140060c52`
- `ntoskrnl!ExReleaseResourceLite` at `0x140060c52`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140060b48`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140060b48`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140060c3f`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140060c3f`

## pseudocode

```c
__int64 __fastcall CscPqEnumContinue(_DWORD *a1, __int64 a2, char a3, int a4)
{
  __int64 v4; // rbx
  int Entry; // edi
  int v8; // ebx
  _QWORD *v9; // r14
  unsigned int v10; // ecx
  __int64 v11; // r8
  unsigned __int64 v12; // rdx
  bool v13; // zf
  char v15; // [rsp+90h] [rbp+18h] BYREF

  v15 = a3;
  v4 = *(_QWORD *)a1;
  v15 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_d46d505bd0f73bc0e95a830c27edc623_Traceguids, a1);
  ExAcquireResourceSharedLite(*(PERESOURCE *)(*(_QWORD *)a1 + 96LL), 1u);
  if ( *(_BYTE *)(v4 + 88) )
  {
    Entry = -1073741596;
    v8 = 254;
  }
  else
  {
    v9 = ExAllocateFromPagedLookasideList(*(PPAGED_LOOKASIDE_LIST *)(*(_QWORD *)a1 + 152LL));
    if ( v9 )
    {
      while ( 1 )
      {
        v10 = a1[8];
        if ( v10 - 1 > 0xFFFFFFFD )
          break;
        if ( v10 > *(_DWORD *)(v4 + 36)
          || (v11 = *(unsigned int *)(v4 + 24),
              v12 = *(unsigned int *)(v4 + 20) + (unsigned __int64)((unsigned int)v11 * (v10 - 1)),
              ((v12 ^ (v12 + v11)) & 0xFFFFFFFFFFFC0000uLL) != 0)
          || !v12 )
        {
          Entry = -1073740768;
          v8 = 290;
          goto LABEL_20;
        }
        Entry = CscPqpReadEntry(v4, v12, v9);
        if ( Entry < 0 )
        {
          v8 = 294;
          goto LABEL_20;
        }
        Entry = CscEnpEvictPqEnumCallback(a4, a1[2], a1[8], *v9, (__int64)(v9 + 5), v9[4], (__int64)&v15);
        if ( Entry < 0 )
        {
          v8 = 303;
          goto LABEL_20;
        }
        v13 = v15 == 0;
        a1[8] = HIDWORD(v9[a1[2] + 1]);
        if ( v13 )
        {
          v8 = 0;
          goto LABEL_20;
        }
      }
      Entry = -2147483622;
      v8 = 279;
LABEL_20:
      ExFreeToPagedLookasideList(*(PPAGED_LOOKASIDE_LIST *)(*(_QWORD *)a1 + 152LL), v9);
    }
    else
    {
      Entry = -1073741670;
      v8 = 266;
    }
  }
  ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)a1 + 96LL));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      WPP_d46d505bd0f73bc0e95a830c27edc623_Traceguids,
      (unsigned int)Entry,
      v8);
  return (unsigned int)Entry;
}

```

## disassembly

```asm
0x140060ac0  mov     rax, rsp
0x140060ac3  mov     [rax+18h], r8b
0x140060ac7  push    rbx
0x140060ac8  push    rbp
0x140060ac9  push    rsi
0x140060aca  push    rdi
0x140060acb  push    r13
0x140060acd  push    r14
0x140060acf  sub     rsp, 48h
0x140060ad3  mov     rbx, [rcx]
0x140060ad6  mov     rbp, r9
0x140060ad9  mov     rsi, rcx
0x140060adc  mov     byte ptr [rax+18h], 0
0x140060ae0  mov     rcx, cs:WPP_GLOBAL_Control
0x140060ae7  lea     r13, WPP_GLOBAL_Control
0x140060aee  cmp     rcx, r13
0x140060af1  jz      short loc_140060B14
0x140060af3  test    dword ptr [rcx+2Ch], 40000h
0x140060afa  jz      short loc_140060B14
0x140060afc  mov     rcx, [rcx+18h]
0x140060b00  lea     r8, WPP_d46d505bd0f73bc0e95a830c27edc623_Traceguids
0x140060b07  mov     edx, 0Eh
0x140060b0c  mov     r9, rsi
0x140060b0f  call    WPP_SF_q
0x140060b14  mov     rcx, [rsi]
0x140060b17  mov     dl, 1; Wait
0x140060b19  mov     rcx, [rcx+60h]; Resource
0x140060b1d  call    cs:__imp_ExAcquireResourceSharedLite
0x140060b24  nop     dword ptr [rax+rax+00h]
0x140060b29  cmp     byte ptr [rbx+58h], 0
0x140060b2d  jz      short loc_140060B3E
0x140060b2f  mov     edi, 0C00000E4h
0x140060b34  mov     ebx, 0FEh
0x140060b39  jmp     loc_140060C4B
0x140060b3e  mov     rcx, [rsi]
0x140060b41  mov     rcx, [rcx+98h]; Lookaside
0x140060b48  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140060b4f  nop     dword ptr [rax+rax+00h]
0x140060b54  mov     r14, rax
0x140060b57  test    rax, rax
0x140060b5a  jnz     short loc_140060B6B
0x140060b5c  mov     edi, 0C000009Ah
0x140060b61  mov     ebx, 10Ah
0x140060b66  jmp     loc_140060C4B
0x140060b6b  mov     ecx, [rsi+20h]
0x140060b6e  lea     eax, [rcx-1]
0x140060b71  cmp     eax, 0FFFFFFFDh
0x140060b74  ja      loc_140060C28
0x140060b7a  cmp     ecx, [rbx+24h]
0x140060b7d  ja      loc_140060C1C
0x140060b83  mov     r8d, [rbx+18h]
0x140060b87  lea     edx, [rcx-1]
0x140060b8a  mov     eax, [rbx+14h]
0x140060b8d  imul    edx, r8d
0x140060b91  add     rdx, rax
0x140060b94  add     r8, rdx
0x140060b97  xor     r8, rdx
0x140060b9a  test    r8, 0FFFFFFFFFFFC0000h
0x140060ba1  jnz     short loc_140060C1C
0x140060ba3  test    rdx, rdx
0x140060ba6  jz      short loc_140060C1C
0x140060ba8  mov     r8, r14
0x140060bab  mov     rcx, rbx
0x140060bae  call    CscPqpReadEntry
0x140060bb3  mov     edi, eax
0x140060bb5  test    eax, eax
0x140060bb7  js      short loc_140060C15
0x140060bb9  mov     r9, [r14]
0x140060bbc  lea     rax, [rsp+78h+arg_10]
0x140060bc4  mov     r8d, [rsi+20h]
0x140060bc8  lea     rcx, [r14+28h]
0x140060bcc  mov     edx, [rsi+8]
0x140060bcf  mov     [rsp+78h+var_48], rax
0x140060bd4  mov     rax, [r14+20h]
0x140060bd8  mov     [rsp+78h+var_50], rax
0x140060bdd  mov     [rsp+78h+var_58], rcx
0x140060be2  mov     rcx, rbp
0x140060be5  call    CscEnpEvictPqEnumCallback
0x140060bea  mov     edi, eax
0x140060bec  test    eax, eax
0x140060bee  js      short loc_140060C0E
0x140060bf0  cmp     [rsp+78h+arg_10], 0
0x140060bf8  movsxd  rax, dword ptr [rsi+8]
0x140060bfc  mov     ecx, [r14+rax*8+0Ch]
0x140060c01  mov     [rsi+20h], ecx
0x140060c04  jnz     loc_140060B6B
0x140060c0a  xor     ebx, ebx
0x140060c0c  jmp     short loc_140060C32
0x140060c0e  mov     ebx, 12Fh
0x140060c13  jmp     short loc_140060C32
0x140060c15  mov     ebx, 126h
0x140060c1a  jmp     short loc_140060C32
0x140060c1c  mov     edi, 0C0000420h
0x140060c21  mov     ebx, 122h
0x140060c26  jmp     short loc_140060C32
0x140060c28  mov     edi, 8000001Ah
0x140060c2d  mov     ebx, 117h
0x140060c32  mov     rcx, [rsi]
0x140060c35  mov     rdx, r14; Entry
0x140060c38  mov     rcx, [rcx+98h]; Lookaside
0x140060c3f  call    cs:__imp_ExFreeToPagedLookasideList
0x140060c46  nop     dword ptr [rax+rax+00h]
0x140060c4b  mov     rcx, [rsi]
0x140060c4e  mov     rcx, [rcx+60h]; Resource
0x140060c52  call    cs:__imp_ExReleaseResourceLite
0x140060c59  nop     dword ptr [rax+rax+00h]
0x140060c5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140060c65  cmp     rcx, r13
0x140060c68  jz      short loc_140060C8F
0x140060c6a  test    dword ptr [rcx+2Ch], 40000h
0x140060c71  jz      short loc_140060C8F
0x140060c73  mov     rcx, [rcx+18h]
0x140060c77  lea     r8, WPP_d46d505bd0f73bc0e95a830c27edc623_Traceguids
0x140060c7e  mov     edx, 0Fh
0x140060c83  mov     dword ptr [rsp+78h+var_58], ebx
0x140060c87  mov     r9d, edi
0x140060c8a  call    WPP_SF_Dd
0x140060c8f  mov     eax, edi
0x140060c91  add     rsp, 48h
0x140060c95  pop     r14
0x140060c97  pop     r13
0x140060c99  pop     rdi
0x140060c9a  pop     rsi
0x140060c9b  pop     rbp
0x140060c9c  pop     rbx
0x140060c9d  retn
```
