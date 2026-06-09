# Smb2ValidateIncomingSignatureForRdmaBuffer

- ea: `0x140033708`
- end: `0x1400339a1`
- name: `Smb2ValidateIncomingSignatureForRdmaBuffer`
- size: `665`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002da60`

## callees

- `0x14002a1dc`
- `0x14002a6a8`
- `0x140033708`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003394d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033985`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003394d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033985`
- `ntoskrnl!RtlCompareMemory` at `0x14003392b`
- `ntoskrnl!RtlCompareMemory` at `0x14003392b`
- `ntoskrnl!ExAllocatePool2` at `0x140033743`
- `ntoskrnl!ExAllocatePool2` at `0x1400338aa`
- `ntoskrnl!ExAllocatePool2` at `0x140033743`
- `ntoskrnl!ExAllocatePool2` at `0x1400338aa`
- `ksecdd!BCryptHashData` at `0x140033882`
- `ksecdd!BCryptHashData` at `0x140033882`
- `ksecdd!BCryptFinishHash` at `0x1400338c9`
- `ksecdd!BCryptFinishHash` at `0x1400338c9`
- `ksecdd!BCryptDuplicateHash` at `0x14003377f`
- `ksecdd!BCryptDuplicateHash` at `0x14003377f`
- `ksecdd!BCryptDestroyHash` at `0x140033963`
- `ksecdd!BCryptDestroyHash` at `0x140033963`
- `ksecdd!BCryptSetProperty` at `0x140033813`
- `ksecdd!BCryptSetProperty` at `0x140033813`

## pseudocode

```c
__int64 __fastcall Smb2ValidateIncomingSignatureForRdmaBuffer(__int64 a1, unsigned __int16 *a2, UCHAR *a3, ULONG a4)
{
  __int64 v8; // rdi
  UCHAR *Pool2; // rax
  UCHAR *v10; // r14
  NTSTATUS v11; // edi
  ULONG v12; // ecx
  UCHAR *v13; // rbp
  SIZE_T v14; // rbx
  BCRYPT_HASH_HANDLE phNewHash; // [rsp+70h] [rbp+8h] BYREF

  v8 = *(_QWORD *)(*(_QWORD *)(a1 + 56) + 96LL);
  phNewHash = 0;
  Pool2 = (UCHAR *)ExAllocatePool2(66, *(unsigned int *)(v8 + 512), 1834184520);
  v10 = Pool2;
  if ( Pool2 )
  {
    v11 = BCryptDuplicateHash(*(BCRYPT_HASH_HANDLE *)(v8 + 496), &phNewHash, Pool2, *(_DWORD *)(v8 + 512), 0);
    if ( v11 >= 0 )
    {
      v12 = a2[2];
      if ( (_WORD)v12 && (v11 = BCryptSetProperty(phNewHash, L"IV", (PUCHAR)a2 + a2[1] + 8, v12, 0), v11 < 0) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qq(
            WPP_GLOBAL_Control->AttachedDevice,
            25,
            WPP_60db1590be613abca80435fd5891bee8_Traceguids,
            *(_QWORD *)(a1 + 56),
            a1);
        }
      }
      else
      {
        v11 = BCryptHashData(phNewHash, a3, a4, 0);
        if ( v11 >= 0 )
        {
          v13 = (UCHAR *)ExAllocatePool2(66, a2[1], 1834182483);
          v11 = BCryptFinishHash(phNewHash, v13, a2[1], 0);
          if ( v11 >= 0 )
          {
            v14 = a2[1];
            if ( v14 != RtlCompareMemory(a2 + 4, v13, v14) )
              v11 = -1073700864;
          }
          else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_qq(
              WPP_GLOBAL_Control->AttachedDevice,
              26,
              WPP_60db1590be613abca80435fd5891bee8_Traceguids,
              *(_QWORD *)(a1 + 56),
              a1);
          }
          if ( v13 )
            ExFreePoolWithTag(v13, 0x6D536753u);
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qqD(
        WPP_GLOBAL_Control->AttachedDevice,
        24,
        WPP_60db1590be613abca80435fd5891bee8_Traceguids,
        *(_QWORD *)(a1 + 56),
        a1,
        v11);
    }
  }
  else
  {
    v11 = -1073741670;
  }
  if ( phNewHash )
  {
    BCryptDestroyHash(phNewHash);
    phNewHash = 0;
  }
  if ( v10 )
    ExFreePoolWithTag(v10, 0x6D536F48u);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140033708  push    rbx
0x14003370a  push    rbp
0x14003370b  push    rsi
0x14003370c  push    rdi
0x14003370d  push    r14
0x14003370f  push    r15
0x140033711  sub     rsp, 38h
0x140033715  mov     rax, [rcx+38h]
0x140033719  mov     r15, r8
0x14003371c  mov     rsi, rdx
0x14003371f  mov     rbx, rcx
0x140033722  mov     ecx, 42h ; 'B'
0x140033727  mov     r8d, 6D536F48h
0x14003372d  mov     ebp, r9d
0x140033730  mov     rdi, [rax+60h]
0x140033734  mov     [rsp+68h+phNewHash], 0
0x14003373d  mov     edx, [rdi+200h]
0x140033743  call    cs:__imp_ExAllocatePool2
0x14003374a  nop     dword ptr [rax+rax+00h]
0x14003374f  mov     r14, rax
0x140033752  test    rax, rax
0x140033755  jnz     short loc_140033761
0x140033757  mov     edi, 0C000009Ah
0x14003375c  jmp     loc_140033959
0x140033761  mov     r9d, [rdi+200h]; cbHashObject
0x140033768  lea     rdx, [rsp+68h+phNewHash]; phNewHash
0x14003376d  mov     rcx, [rdi+1F0h]; hHash
0x140033774  mov     r8, r14; pbHashObject
0x140033777  mov     [rsp+68h+dwFlags], 0; dwFlags
0x14003377f  call    cs:__imp_BCryptDuplicateHash
0x140033786  nop     dword ptr [rax+rax+00h]
0x14003378b  mov     edi, eax
0x14003378d  test    eax, eax
0x14003378f  jns     short loc_1400337E5
0x140033791  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140033798  lea     rax, WPP_GLOBAL_Control
0x14003379f  cmp     rcx, rax
0x1400337a2  jz      loc_140033959
0x1400337a8  mov     edx, [rcx+2Ch]
0x1400337ab  test    dl, 1
0x1400337ae  jz      loc_140033959
0x1400337b4  cmp     byte ptr [rcx+29h], 1
0x1400337b8  jb      loc_140033959
0x1400337be  mov     r9, [rbx+38h]
0x1400337c2  lea     r8, WPP_60db1590be613abca80435fd5891bee8_Traceguids
0x1400337c9  mov     rcx, [rcx+18h]
0x1400337cd  mov     edx, 18h
0x1400337d2  mov     [rsp+68h+var_40], edi
0x1400337d6  mov     qword ptr [rsp+68h+dwFlags], rbx
0x1400337db  call    WPP_SF_qqD
0x1400337e0  jmp     loc_140033959
0x1400337e5  movzx   ecx, word ptr [rsi+4]
0x1400337e9  xor     eax, eax
0x1400337eb  cmp     ax, cx
0x1400337ee  jnb     loc_140033874
0x1400337f4  movzx   r8d, word ptr [rsi+2]
0x1400337f9  lea     rdx, pszProperty; "IV"
0x140033800  add     r8, 8
0x140033804  mov     [rsp+68h+dwFlags], eax; dwFlags
0x140033808  mov     r9d, ecx; cbInput
0x14003380b  add     r8, rsi; pbInput
0x14003380e  mov     rcx, [rsp+68h+phNewHash]; hObject
0x140033813  call    cs:__imp_BCryptSetProperty
0x14003381a  nop     dword ptr [rax+rax+00h]
0x14003381f  mov     edi, eax
0x140033821  test    eax, eax
0x140033823  jns     short loc_140033874
0x140033825  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003382c  lea     rax, WPP_GLOBAL_Control
0x140033833  cmp     rcx, rax
0x140033836  jz      loc_140033959
0x14003383c  mov     eax, [rcx+2Ch]
0x14003383f  test    al, 1
0x140033841  jz      loc_140033959
0x140033847  cmp     byte ptr [rcx+29h], 1
0x14003384b  jb      loc_140033959
0x140033851  mov     r9, [rbx+38h]
0x140033855  lea     r8, WPP_60db1590be613abca80435fd5891bee8_Traceguids
0x14003385c  mov     rcx, [rcx+18h]
0x140033860  mov     edx, 19h
0x140033865  mov     qword ptr [rsp+68h+dwFlags], rbx
0x14003386a  call    WPP_SF_qq
0x14003386f  jmp     loc_140033959
0x140033874  mov     rcx, [rsp+68h+phNewHash]; hHash
0x140033879  xor     r9d, r9d; dwFlags
0x14003387c  mov     r8d, ebp; cbInput
0x14003387f  mov     rdx, r15; pbInput
0x140033882  call    cs:__imp_BCryptHashData
0x140033889  nop     dword ptr [rax+rax+00h]
0x14003388e  mov     edi, eax
0x140033890  test    eax, eax
0x140033892  js      loc_140033959
0x140033898  movzx   edx, word ptr [rsi+2]
0x14003389c  mov     r15d, 6D536753h
0x1400338a2  mov     r8d, r15d
0x1400338a5  mov     ecx, 42h ; 'B'
0x1400338aa  call    cs:__imp_ExAllocatePool2
0x1400338b1  nop     dword ptr [rax+rax+00h]
0x1400338b6  movzx   r8d, word ptr [rsi+2]; cbOutput
0x1400338bb  xor     r9d, r9d; dwFlags
0x1400338be  mov     rcx, [rsp+68h+phNewHash]; hHash
0x1400338c3  mov     rdx, rax; pbOutput
0x1400338c6  mov     rbp, rax
0x1400338c9  call    cs:__imp_BCryptFinishHash
0x1400338d0  nop     dword ptr [rax+rax+00h]
0x1400338d5  mov     edi, eax
0x1400338d7  test    eax, eax
0x1400338d9  jns     short loc_14003391B
0x1400338db  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400338e2  lea     rax, WPP_GLOBAL_Control
0x1400338e9  cmp     rcx, rax
0x1400338ec  jz      short loc_140033942
0x1400338ee  mov     eax, [rcx+2Ch]
0x1400338f1  test    al, 1
0x1400338f3  jz      short loc_140033942
0x1400338f5  cmp     byte ptr [rcx+29h], 1
0x1400338f9  jb      short loc_140033942
0x1400338fb  mov     r9, [rbx+38h]
0x1400338ff  lea     r8, WPP_60db1590be613abca80435fd5891bee8_Traceguids
0x140033906  mov     rcx, [rcx+18h]
0x14003390a  mov     edx, 1Ah
0x14003390f  mov     qword ptr [rsp+68h+dwFlags], rbx
0x140033914  call    WPP_SF_qq
0x140033919  jmp     short loc_140033942
0x14003391b  movzx   r8d, word ptr [rsi+2]; Length
0x140033920  lea     rcx, [rsi+8]; Source1
0x140033924  movzx   ebx, word ptr [rsi+2]
0x140033928  mov     rdx, rbp; Source2
0x14003392b  call    cs:__imp_RtlCompareMemory
0x140033932  nop     dword ptr [rax+rax+00h]
0x140033937  cmp     rbx, rax
0x14003393a  mov     ecx, 0C000A000h
0x14003393f  cmovnz  edi, ecx
0x140033942  test    rbp, rbp
0x140033945  jz      short loc_140033959
0x140033947  mov     edx, r15d; Tag
0x14003394a  mov     rcx, rbp; P
0x14003394d  call    cs:__imp_ExFreePoolWithTag
0x140033954  nop     dword ptr [rax+rax+00h]
0x140033959  mov     rcx, [rsp+68h+phNewHash]; hHash
0x14003395e  test    rcx, rcx
0x140033961  jz      short loc_140033978
0x140033963  call    cs:__imp_BCryptDestroyHash
0x14003396a  nop     dword ptr [rax+rax+00h]
0x14003396f  mov     [rsp+68h+phNewHash], 0
0x140033978  test    r14, r14
0x14003397b  jz      short loc_140033991
0x14003397d  mov     edx, 6D536F48h; Tag
0x140033982  mov     rcx, r14; P
0x140033985  call    cs:__imp_ExFreePoolWithTag
0x14003398c  nop     dword ptr [rax+rax+00h]
0x140033991  mov     eax, edi
0x140033993  add     rsp, 38h
0x140033997  pop     r15
0x140033999  pop     r14
0x14003399b  pop     rdi
0x14003399c  pop     rsi
0x14003399d  pop     rbp
0x14003399e  pop     rbx
0x14003399f  retn
```
