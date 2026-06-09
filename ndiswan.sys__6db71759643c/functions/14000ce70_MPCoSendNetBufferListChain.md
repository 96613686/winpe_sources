# MPCoSendNetBufferListChain

- ea: `0x14000ce70`
- end: `0x14000d0b3`
- name: `MPCoSendNetBufferListChain`
- size: `579`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140001be0`
- `0x14000a290`
- `0x14000a2c0`
- `0x14000a648`
- `0x14000ce70`
- `0x140016700`

## import_xrefs

- `NDIS!NdisMSendNetBufferListsComplete` at `0x14000d065`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x14000d065`
- `NDIS!NdisAllocateNetBufferListContext` at `0x14000cfb1`
- `NDIS!NdisAllocateNetBufferListContext` at `0x14000cfb1`

## pseudocode

```c
void __fastcall MPCoSendNetBufferListChain(__int64 a1, struct _NET_BUFFER_LIST *Alignment)
{
  __int64 v2; // rax
  __int64 v5; // r15
  __int64 v6; // r9
  struct _NET_BUFFER_LIST *v7; // rax
  __int64 v8; // r9
  struct _NET_BUFFER_LIST *v9; // rax
  _QWORD *p_Alignment; // r14
  SLIST_HEADER *v11; // rax
  struct _NET_BUFFER_LIST *v12; // rsi
  char *v13; // rbx
  struct _NET_BUFFER_LIST *v14; // [rsp+50h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 56);
  v14 = 0;
  v5 = *(_QWORD *)(v2 + 24);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_57c91ebf850d312e4ec0e2452bcf32f2_Traceguids);
  }
  v6 = *(unsigned int *)(a1 + 20);
  if ( (_DWORD)v6 == 1 )
  {
    v8 = *(unsigned int *)(v5 + 20);
    if ( !(_DWORD)v8 )
    {
      p_Alignment = &v14;
      if ( !Alignment )
        goto LABEL_33;
      do
      {
        v11 = (SLIST_HEADER *)Alignment;
        v12 = Alignment;
        Alignment = (struct _NET_BUFFER_LIST *)Alignment->Link.Alignment;
        v11->Alignment = 0;
        if ( NdisAllocateNetBufferListContext(v12, 0x80u, 0, 0x444E6157u) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_57c91ebf850d312e4ec0e2452bcf32f2_Traceguids, v12);
          }
          v12->Status = -1073741670;
          *p_Alignment = v12;
          p_Alignment = &v12->Link.Alignment;
        }
        else
        {
          v13 = (char *)v12->Context + v12->Context->Offset;
          memset(v13 + 16, 0, 0x80u);
          _InterlockedIncrement((volatile signed __int32 *)(a1 + 24));
          *((_QWORD *)v13 + 11) = a1;
          *((_QWORD *)v13 + 17) = v12->SourceHandle;
          *((_DWORD *)v13 + 8) = 1684956499;
          ApplyQoSAndQueueSend(v5, v12);
        }
      }
      while ( Alignment );
      Alignment = v14;
      goto LABEL_31;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_57c91ebf850d312e4ec0e2452bcf32f2_Traceguids, v8);
    }
    v9 = Alignment;
    if ( Alignment )
    {
      do
      {
        v9->Status = -1071448022;
        v9 = (struct _NET_BUFFER_LIST *)v9->Link.Alignment;
      }
      while ( v9 );
LABEL_31:
      if ( Alignment )
        NdisMSendNetBufferListsComplete(*(NDIS_HANDLE *)(a1 + 40), Alignment, 0);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_57c91ebf850d312e4ec0e2452bcf32f2_Traceguids, v6);
    }
    v7 = Alignment;
    if ( Alignment )
    {
      do
      {
        v7->Status = -1073741823;
        v7 = (struct _NET_BUFFER_LIST *)v7->Link.Alignment;
      }
      while ( v7 );
      goto LABEL_31;
    }
  }
LABEL_33:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_57c91ebf850d312e4ec0e2452bcf32f2_Traceguids);
  }
}

```

## disassembly

```asm
0x14000ce70  mov     [rsp+arg_8], rbx
0x14000ce75  mov     [rsp+arg_10], rbp
0x14000ce7a  push    rsi
0x14000ce7b  push    rdi
0x14000ce7c  push    r13
0x14000ce7e  push    r14
0x14000ce80  push    r15
0x14000ce82  sub     rsp, 20h
0x14000ce86  mov     rax, [rcx+38h]
0x14000ce8a  mov     rdi, rdx
0x14000ce8d  mov     rbp, rcx
0x14000ce90  mov     [rsp+48h+arg_0], 0
0x14000ce99  mov     r15, [rax+18h]
0x14000ce9d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cea4  lea     r13, WPP_GLOBAL_Control
0x14000ceab  lea     rbx, WPP_57c91ebf850d312e4ec0e2452bcf32f2_Traceguids
0x14000ceb2  cmp     rcx, r13
0x14000ceb5  jz      short loc_14000CED5
0x14000ceb7  mov     eax, [rcx+2Ch]
0x14000ceba  test    al, 8
0x14000cebc  jz      short loc_14000CED5
0x14000cebe  cmp     byte ptr [rcx+29h], 5
0x14000cec2  jb      short loc_14000CED5
0x14000cec4  mov     rcx, [rcx+18h]
0x14000cec8  mov     edx, 28h ; '('
0x14000cecd  mov     r8, rbx
0x14000ced0  call    WPP_SF_
0x14000ced5  mov     r9d, [rbp+14h]
0x14000ced9  cmp     r9d, 1
0x14000cedd  jz      short loc_14000CF2C
0x14000cedf  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cee6  cmp     rcx, r13
0x14000cee9  jz      short loc_14000CF09
0x14000ceeb  mov     eax, [rcx+2Ch]
0x14000ceee  test    al, 8
0x14000cef0  jz      short loc_14000CF09
0x14000cef2  cmp     byte ptr [rcx+29h], 5
0x14000cef6  jb      short loc_14000CF09
0x14000cef8  mov     rcx, [rcx+18h]
0x14000cefc  mov     edx, 29h ; ')'
0x14000cf01  mov     r8, rbx
0x14000cf04  call    WPP_SF_d
0x14000cf09  mov     rax, rdi
0x14000cf0c  test    rdi, rdi
0x14000cf0f  jz      loc_14000D071
0x14000cf15  mov     dword ptr [rax+8Ch], 0C0000001h
0x14000cf1f  mov     rax, [rax]
0x14000cf22  test    rax, rax
0x14000cf25  jnz     short loc_14000CF15
0x14000cf27  jmp     loc_14000D056
0x14000cf2c  mov     r9d, [r15+14h]
0x14000cf30  test    r9d, r9d
0x14000cf33  jz      short loc_14000CF82
0x14000cf35  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cf3c  cmp     rcx, r13
0x14000cf3f  jz      short loc_14000CF5F
0x14000cf41  mov     eax, [rcx+2Ch]
0x14000cf44  test    al, 8
0x14000cf46  jz      short loc_14000CF5F
0x14000cf48  cmp     byte ptr [rcx+29h], 5
0x14000cf4c  jb      short loc_14000CF5F
0x14000cf4e  mov     rcx, [rcx+18h]
0x14000cf52  mov     edx, 2Ah ; '*'
0x14000cf57  mov     r8, rbx
0x14000cf5a  call    WPP_SF_d
0x14000cf5f  mov     rax, rdi
0x14000cf62  test    rdi, rdi
0x14000cf65  jz      loc_14000D071
0x14000cf6b  mov     dword ptr [rax+8Ch], 0C023002Ah
0x14000cf75  mov     rax, [rax]
0x14000cf78  test    rax, rax
0x14000cf7b  jnz     short loc_14000CF6B
0x14000cf7d  jmp     loc_14000D056
0x14000cf82  lea     r14, [rsp+48h+arg_0]
0x14000cf87  test    rdi, rdi
0x14000cf8a  jz      loc_14000D071
0x14000cf90  mov     rax, rdi
0x14000cf93  mov     rsi, rdi
0x14000cf96  mov     rdi, [rdi]
0x14000cf99  xor     r8d, r8d; ContextBackFill
0x14000cf9c  mov     edx, 80h; ContextSize
0x14000cfa1  mov     r9d, 444E6157h; PoolTag
0x14000cfa7  mov     rcx, rsi; NetBufferList
0x14000cfaa  mov     qword ptr [rax], 0
0x14000cfb1  call    cs:__imp_NdisAllocateNetBufferListContext
0x14000cfb8  nop     dword ptr [rax+rax+00h]
0x14000cfbd  test    eax, eax
0x14000cfbf  jz      short loc_14000D000
0x14000cfc1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cfc8  cmp     rcx, r13
0x14000cfcb  jz      short loc_14000CFEE
0x14000cfcd  mov     eax, [rcx+2Ch]
0x14000cfd0  test    al, 8
0x14000cfd2  jz      short loc_14000CFEE
0x14000cfd4  cmp     byte ptr [rcx+29h], 3
0x14000cfd8  jb      short loc_14000CFEE
0x14000cfda  mov     rcx, [rcx+18h]
0x14000cfde  mov     edx, 2Bh ; '+'
0x14000cfe3  mov     r9, rsi
0x14000cfe6  mov     r8, rbx
0x14000cfe9  call    WPP_SF_q
0x14000cfee  mov     dword ptr [rsi+8Ch], 0C000009Ah
0x14000cff8  mov     [r14], rsi
0x14000cffb  mov     r14, rsi
0x14000cffe  jmp     short loc_14000D048
0x14000d000  mov     rcx, [rsi+10h]
0x14000d004  xor     edx, edx; Val
0x14000d006  mov     r8d, 80h; Size
0x14000d00c  movzx   ebx, word ptr [rcx+0Ah]
0x14000d010  add     rbx, rcx
0x14000d013  lea     rcx, [rbx+10h]; void *
0x14000d017  call    memset
0x14000d01c  lock inc dword ptr [rbp+18h]
0x14000d020  mov     [rbx+58h], rbp
0x14000d024  mov     rdx, rsi
0x14000d027  mov     rax, [rsi+78h]
0x14000d02b  mov     rcx, r15
0x14000d02e  mov     [rbx+88h], rax
0x14000d035  mov     dword ptr [rbx+20h], 646E6553h
0x14000d03c  call    ApplyQoSAndQueueSend
0x14000d041  lea     rbx, WPP_57c91ebf850d312e4ec0e2452bcf32f2_Traceguids
0x14000d048  test    rdi, rdi
0x14000d04b  jnz     loc_14000CF90
0x14000d051  mov     rdi, [rsp+48h+arg_0]
0x14000d056  test    rdi, rdi
0x14000d059  jz      short loc_14000D071
0x14000d05b  mov     rcx, [rbp+28h]; MiniportAdapterHandle
0x14000d05f  xor     r8d, r8d; SendCompleteFlags
0x14000d062  mov     rdx, rdi; NetBufferList
0x14000d065  call    cs:__imp_NdisMSendNetBufferListsComplete
0x14000d06c  nop     dword ptr [rax+rax+00h]
0x14000d071  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d078  cmp     rcx, r13
0x14000d07b  jz      short loc_14000D09B
0x14000d07d  mov     eax, [rcx+2Ch]
0x14000d080  test    al, 8
0x14000d082  jz      short loc_14000D09B
0x14000d084  cmp     byte ptr [rcx+29h], 5
0x14000d088  jb      short loc_14000D09B
0x14000d08a  mov     rcx, [rcx+18h]
0x14000d08e  mov     edx, 2Ch ; ','
0x14000d093  mov     r8, rbx
0x14000d096  call    WPP_SF_
0x14000d09b  mov     rbx, [rsp+48h+arg_8]
0x14000d0a0  mov     rbp, [rsp+48h+arg_10]
0x14000d0a5  add     rsp, 20h
0x14000d0a9  pop     r15
0x14000d0ab  pop     r14
0x14000d0ad  pop     r13
0x14000d0af  pop     rdi
0x14000d0b0  pop     rsi
0x14000d0b1  retn
```
