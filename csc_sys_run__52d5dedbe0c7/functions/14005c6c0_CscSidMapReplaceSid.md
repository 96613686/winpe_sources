# CscSidMapReplaceSid

- ea: `0x14005c6c0`
- end: `0x14005c8a1`
- name: `CscSidMapReplaceSid`
- size: `481`
- prototype: `__int64 __fastcall(__int64, void *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140023604`

## callees

- `0x140018930`
- `0x14001b568`
- `0x14002f140`
- `0x14005c6c0`
- `0x14005cac4`
- `0x14007fb70`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14005c7af`
- `ntoskrnl!ExAllocatePool2` at `0x14005c7af`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c81e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c81e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c837`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c850`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c837`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c850`
- `ntoskrnl!RtlLengthSid` at `0x14005c772`
- `ntoskrnl!RtlLengthSid` at `0x14005c784`
- `ntoskrnl!RtlLengthSid` at `0x14005c772`
- `ntoskrnl!RtlLengthSid` at `0x14005c784`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005c723`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005c723`

## pseudocode

```c
__int64 __fastcall CscSidMapReplaceSid(__int64 a1, void *a2, void *a3)
{
  void *v3; // rdi
  void *v6; // rsi
  __int64 v7; // rbp
  __int64 HaveLock; // r12
  int v9; // ebx
  ULONG v10; // r13d
  ULONG v11; // eax
  __int64 v12; // r15
  __int64 v13; // r9
  void *Pool2; // rax
  ULONG v16; // [rsp+70h] [rbp+8h]
  size_t Size; // [rsp+88h] [rbp+20h]

  v3 = 0;
  v6 = 0;
  v7 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 56LL);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_238132d70db8346a917bc6570ec5eca2_Traceguids, a2, a3);
  ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v7 + 8), 1u);
  HaveLock = (unsigned __int16)CscSidMappLookupIndexBySidHaveLock(v7, a2);
  if ( (_WORD)HaveLock )
  {
    if ( (unsigned __int16)CscSidMappLookupIndexBySidHaveLock(v7, a3) )
    {
      v9 = -1073741771;
    }
    else
    {
      v10 = RtlLengthSid(a2);
      v11 = RtlLengthSid(a3);
      v12 = *(_QWORD *)(v7 + 56);
      v16 = v11;
      Size = v11;
      Pool2 = (void *)ExAllocatePool2(258, v11, 591426371, v13);
      v3 = Pool2;
      if ( Pool2 )
      {
        memmove(Pool2, a3, Size);
        v6 = *(void **)(v12 + 16 * HaveLock);
        *(_DWORD *)(v12 + 16 * HaveLock - 8) = v16;
        *(_QWORD *)(v12 + 16 * HaveLock) = v3;
        v9 = CscSidMappSave(v7, 1);
        if ( v9 >= 0 )
        {
          v3 = 0;
        }
        else
        {
          *(_QWORD *)(v12 + 16 * HaveLock) = v6;
          v6 = 0;
          *(_DWORD *)(v12 + 16 * HaveLock - 8) = v10;
        }
      }
      else
      {
        v9 = -1073741670;
      }
    }
  }
  else
  {
    v9 = -1073741772;
  }
  ExReleaseResourceLite(*(PERESOURCE *)(v7 + 8));
  if ( v6 )
    ExFreePoolWithTag(v6, 0x23407343u);
  if ( v3 )
    ExFreePoolWithTag(v3, 0x23407343u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_238132d70db8346a917bc6570ec5eca2_Traceguids, (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14005c6c0  mov     [rsp+arg_8], rbx
0x14005c6c5  push    rbp
0x14005c6c6  push    rsi
0x14005c6c7  push    rdi
0x14005c6c8  push    r12
0x14005c6ca  push    r13
0x14005c6cc  push    r14
0x14005c6ce  push    r15
0x14005c6d0  sub     rsp, 30h
0x14005c6d4  mov     rax, [rcx+8]
0x14005c6d8  xor     edi, edi
0x14005c6da  mov     rbx, r8
0x14005c6dd  mov     r14, rdx
0x14005c6e0  xor     esi, esi
0x14005c6e2  mov     rbp, [rax+38h]
0x14005c6e6  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c6ed  lea     r15, WPP_GLOBAL_Control
0x14005c6f4  cmp     rcx, r15
0x14005c6f7  jz      short loc_14005C71D
0x14005c6f9  test    dword ptr [rcx+2Ch], 40000h
0x14005c700  jz      short loc_14005C71D
0x14005c702  mov     rcx, [rcx+18h]
0x14005c706  lea     edx, [rdi+15h]
0x14005c709  mov     r9, r14
0x14005c70c  mov     [rsp+68h+var_48], rbx
0x14005c711  lea     r8, WPP_238132d70db8346a917bc6570ec5eca2_Traceguids
0x14005c718  call    WPP_SF_qq
0x14005c71d  mov     rcx, [rbp+8]; Resource
0x14005c721  mov     dl, 1; Wait
0x14005c723  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14005c72a  nop     dword ptr [rax+rax+00h]
0x14005c72f  mov     rdx, r14
0x14005c732  mov     rcx, rbp
0x14005c735  call    CscSidMappLookupIndexBySidHaveLock
0x14005c73a  movzx   r12d, ax
0x14005c73e  xor     eax, eax
0x14005c740  cmp     ax, r12w
0x14005c744  jnz     short loc_14005C750
0x14005c746  mov     ebx, 0C0000034h
0x14005c74b  jmp     loc_14005C81A
0x14005c750  mov     rdx, rbx
0x14005c753  mov     rcx, rbp
0x14005c756  call    CscSidMappLookupIndexBySidHaveLock
0x14005c75b  movzx   ecx, ax
0x14005c75e  xor     eax, eax
0x14005c760  cmp     ax, cx
0x14005c763  jz      short loc_14005C76F
0x14005c765  mov     ebx, 0C0000035h
0x14005c76a  jmp     loc_14005C81A
0x14005c76f  mov     rcx, r14; Sid
0x14005c772  call    cs:__imp_RtlLengthSid
0x14005c779  nop     dword ptr [rax+rax+00h]
0x14005c77e  mov     rcx, rbx; Sid
0x14005c781  mov     r13d, eax
0x14005c784  call    cs:__imp_RtlLengthSid
0x14005c78b  nop     dword ptr [rax+rax+00h]
0x14005c790  mov     r15, [rbp+38h]
0x14005c794  mov     r8d, 23407343h
0x14005c79a  mov     [rsp+68h+arg_0], eax
0x14005c79e  mov     ecx, 102h
0x14005c7a3  mov     eax, eax
0x14005c7a5  mov     edx, eax
0x14005c7a7  mov     [rsp+68h+Size], rax
0x14005c7af  call    cs:__imp_ExAllocatePool2
0x14005c7b6  nop     dword ptr [rax+rax+00h]
0x14005c7bb  mov     rdi, rax
0x14005c7be  test    rax, rax
0x14005c7c1  jz      short loc_14005C80E
0x14005c7c3  mov     r8, [rsp+68h+Size]; Size
0x14005c7cb  mov     r14, r12
0x14005c7ce  mov     rdx, rbx; Src
0x14005c7d1  mov     rcx, rax; void *
0x14005c7d4  add     r14, r14
0x14005c7d7  call    memmove
0x14005c7dc  mov     eax, [rsp+68h+arg_0]
0x14005c7e0  mov     dl, 1
0x14005c7e2  mov     rsi, [r15+r14*8]
0x14005c7e6  mov     rcx, rbp
0x14005c7e9  mov     [r15+r14*8-8], eax
0x14005c7ee  mov     [r15+r14*8], rdi
0x14005c7f2  call    CscSidMappSave
0x14005c7f7  mov     ebx, eax
0x14005c7f9  test    eax, eax
0x14005c7fb  jns     short loc_14005C80A
0x14005c7fd  mov     [r15+r14*8], rsi
0x14005c801  xor     esi, esi
0x14005c803  mov     [r15+r14*8-8], r13d
0x14005c808  jmp     short loc_14005C813
0x14005c80a  xor     edi, edi
0x14005c80c  jmp     short loc_14005C813
0x14005c80e  mov     ebx, 0C000009Ah
0x14005c813  lea     r15, WPP_GLOBAL_Control
0x14005c81a  mov     rcx, [rbp+8]; Resource
0x14005c81e  call    cs:__imp_ExReleaseResourceLite
0x14005c825  nop     dword ptr [rax+rax+00h]
0x14005c82a  test    rsi, rsi
0x14005c82d  jz      short loc_14005C843
0x14005c82f  mov     edx, 23407343h; Tag
0x14005c834  mov     rcx, rsi; P
0x14005c837  call    cs:__imp_ExFreePoolWithTag
0x14005c83e  nop     dword ptr [rax+rax+00h]
0x14005c843  test    rdi, rdi
0x14005c846  jz      short loc_14005C85C
0x14005c848  mov     edx, 23407343h; Tag
0x14005c84d  mov     rcx, rdi; P
0x14005c850  call    cs:__imp_ExFreePoolWithTag
0x14005c857  nop     dword ptr [rax+rax+00h]
0x14005c85c  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c863  cmp     rcx, r15
0x14005c866  jz      short loc_14005C889
0x14005c868  test    dword ptr [rcx+2Ch], 40000h
0x14005c86f  jz      short loc_14005C889
0x14005c871  mov     rcx, [rcx+18h]
0x14005c875  lea     r8, WPP_238132d70db8346a917bc6570ec5eca2_Traceguids
0x14005c87c  mov     edx, 16h
0x14005c881  mov     r9d, ebx
0x14005c884  call    WPP_SF_d
0x14005c889  mov     eax, ebx
0x14005c88b  mov     rbx, [rsp+68h+arg_8]
0x14005c890  add     rsp, 30h
0x14005c894  pop     r15
0x14005c896  pop     r14
0x14005c898  pop     r13
0x14005c89a  pop     r12
0x14005c89c  pop     rdi
0x14005c89d  pop     rsi
0x14005c89e  pop     rbp
0x14005c89f  retn
```
