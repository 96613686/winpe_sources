# DepFSForEachDependency

- ea: `0x18000bb48`
- end: `0x18000bcc2`
- name: `DepFSForEachDependency`
- size: `378`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180001610`
- `0x18000baa0`

## callees

- `0x180001020`
- `0x18000b964`
- `0x18000bb48`
- `0x18000d9d0`
- `0x18000f5f8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18000bba1`
- `ntoskrnl!ExAllocatePool2` at `0x18000bba1`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000bb7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000bc67`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000bb7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000bc67`

## pseudocode

```c
__int64 __fastcall DepFSForEachDependency(__int64 a1)
{
  _QWORD *Pool2; // rdi
  unsigned int v3; // esi
  __int64 v4; // rbx
  __int64 v5; // rdx
  int v6; // eax
  unsigned int v7; // ebx
  int v9; // [rsp+70h] [rbp+18h] BYREF

  Pool2 = 0;
  v9 = 3;
  v3 = 72;
  while ( 1 )
  {
    if ( Pool2 )
    {
      v4 = Pool2[1];
      ExFreePoolWithTag(Pool2, 0x72517044u);
      v3 = v4;
      if ( v4 != (unsigned int)v4 )
        return (unsigned int)-1073741670;
    }
    Pool2 = (_QWORD *)ExAllocatePool2(256, v3, 1917939780);
    if ( !Pool2 )
      break;
    v6 = DepFSSendIoctl(a1, v5, &v9);
    if ( v6 != -2147483643 )
    {
      v7 = 0;
      if ( v6 < 0 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_D(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x28u,
          (__int64)WPP_bc64936b77293105c4440102cf4189d6_Traceguids,
          v6);
      ExFreePoolWithTag(Pool2, 0x72517044u);
      return v7;
    }
  }
  v7 = -1073741670;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_D(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x27u,
      (__int64)WPP_bc64936b77293105c4440102cf4189d6_Traceguids,
      v3);
  }
  return v7;
}

```

## disassembly

```asm
0x18000bb48  mov     rax, rsp
0x18000bb4b  mov     [rax+8], rbx
0x18000bb4f  mov     [rax+10h], rdx
0x18000bb53  push    rbp
0x18000bb54  push    rsi
0x18000bb55  push    rdi
0x18000bb56  sub     rsp, 40h
0x18000bb5a  xor     edi, edi
0x18000bb5c  mov     dword ptr [rax+18h], 3
0x18000bb63  mov     rbp, rcx
0x18000bb66  mov     [rax+10h], edi
0x18000bb69  lea     esi, [rdi+48h]
0x18000bb6c  test    rdi, rdi
0x18000bb6f  jz      short loc_18000BB94
0x18000bb71  mov     rbx, [rdi+8]
0x18000bb75  mov     edx, 72517044h; Tag
0x18000bb7a  mov     rcx, rdi; P
0x18000bb7d  call    cs:__imp_ExFreePoolWithTag
0x18000bb84  nop     dword ptr [rax+rax+00h]
0x18000bb89  mov     esi, ebx
0x18000bb8b  cmp     rbx, rsi
0x18000bb8e  jnz     loc_18000BC30
0x18000bb94  mov     edx, esi
0x18000bb96  mov     ecx, 100h
0x18000bb9b  mov     r8d, 72517044h
0x18000bba1  call    cs:__imp_ExAllocatePool2
0x18000bba8  nop     dword ptr [rax+rax+00h]
0x18000bbad  mov     rdi, rax
0x18000bbb0  test    rax, rax
0x18000bbb3  jz      loc_18000BC75
0x18000bbb9  lea     rax, [rsp+58h+arg_8]
0x18000bbbe  mov     rcx, rbp
0x18000bbc1  mov     [rsp+58h+var_28], rax
0x18000bbc6  lea     r8, [rsp+58h+arg_10]
0x18000bbcb  mov     [rsp+58h+var_30], esi
0x18000bbcf  mov     [rsp+58h+var_38], rdi
0x18000bbd4  call    DepFSSendIoctl
0x18000bbd9  mov     r9d, eax
0x18000bbdc  cmp     eax, 80000005h
0x18000bbe1  jz      short loc_18000BB6C
0x18000bbe3  xor     ebx, ebx
0x18000bbe5  test    eax, eax
0x18000bbe7  js      short loc_18000BC37
0x18000bbe9  cmp     [rsp+58h+arg_8], 38h ; '8'
0x18000bbee  jb      short loc_18000BC5F
0x18000bbf0  xor     esi, esi
0x18000bbf2  cmp     [rdi+4], ebx
0x18000bbf5  jbe     short loc_18000BC5F
0x18000bbf7  mov     eax, esi
0x18000bbf9  inc     rax
0x18000bbfc  lea     rax, [rax+rax*2]
0x18000bc00  add     rax, rax
0x18000bc03  mov     rbp, [rdi+rax*8]
0x18000bc07  test    rbp, rbp
0x18000bc0a  jz      short loc_18000BC27
0x18000bc0c  mov     eax, 3030h
0x18000bc11  cmp     [rbp+0], ax
0x18000bc15  jnz     short loc_18000BC27
0x18000bc17  mov     rcx, rbp
0x18000bc1a  call    DepFSDecrementActiveMountCount
0x18000bc1f  mov     rcx, rbp; P
0x18000bc22  call    DependentFSDereferenceDependency
0x18000bc27  inc     esi
0x18000bc29  cmp     esi, [rdi+4]
0x18000bc2c  jb      short loc_18000BBF7
0x18000bc2e  jmp     short loc_18000BC5F
0x18000bc30  mov     ebx, 0C000009Ah
0x18000bc35  jmp     short loc_18000BCB2
0x18000bc37  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc3e  lea     rax, WPP_GLOBAL_Control
0x18000bc45  cmp     rcx, rax
0x18000bc48  jz      short loc_18000BC5F
0x18000bc4a  mov     rcx, [rcx+18h]
0x18000bc4e  lea     r8, WPP_bc64936b77293105c4440102cf4189d6_Traceguids
0x18000bc55  mov     edx, 28h ; '('
0x18000bc5a  call    WPP_SF_D
0x18000bc5f  mov     edx, 72517044h; Tag
0x18000bc64  mov     rcx, rdi; P
0x18000bc67  call    cs:__imp_ExFreePoolWithTag
0x18000bc6e  nop     dword ptr [rax+rax+00h]
0x18000bc73  jmp     short loc_18000BCB2
0x18000bc75  mov     ebx, 0C000009Ah
0x18000bc7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc81  lea     rax, WPP_GLOBAL_Control
0x18000bc88  cmp     rcx, rax
0x18000bc8b  jz      short loc_18000BCB2
0x18000bc8d  mov     eax, [rcx+2Ch]
0x18000bc90  test    al, 1
0x18000bc92  jz      short loc_18000BCB2
0x18000bc94  cmp     byte ptr [rcx+29h], 2
0x18000bc98  jb      short loc_18000BCB2
0x18000bc9a  mov     rcx, [rcx+18h]
0x18000bc9e  lea     r8, WPP_bc64936b77293105c4440102cf4189d6_Traceguids
0x18000bca5  mov     edx, 27h ; '''
0x18000bcaa  mov     r9d, esi
0x18000bcad  call    WPP_SF_D
0x18000bcb2  mov     eax, ebx
0x18000bcb4  mov     rbx, [rsp+58h+arg_0]
0x18000bcb9  add     rsp, 40h
0x18000bcbd  pop     rdi
0x18000bcbe  pop     rsi
0x18000bcbf  pop     rbp
0x18000bcc0  retn
```
