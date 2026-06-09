# CheckBSQHeadForCompletion

- ea: `0x180023cc0`
- end: `0x180023dc7`
- name: `CheckBSQHeadForCompletion`
- size: `263`
- prototype: `__int64 __fastcall(PVOID CompletionContext)`
- caller_count: `6`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003c7cc`
- `0x18003ff84`
- `0x1800411a8`
- `0x180045cfc`
- `0x180046c34`
- `0x180049ba8`

## callees

- `0x180023cc0`
- `0x180023f14`
- `0x180024dd4`
- `0x18003f28c`
- `0x18003f2e0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180023d6a`
- `ntdll!RtlFreeHeap` at `0x180023d6a`

## pseudocode

```c
void __fastcall CheckBSQHeadForCompletion(_QWORD *CompletionContext)
{
  _QWORD *v1; // rax
  _QWORD *v3; // rcx
  _QWORD *v4; // rdi
  __int64 v5; // rdx
  _DWORD *v6; // rsi
  char *v7; // r8
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  char *v10; // rax

  v1 = CompletionContext + 50;
  v3 = (_QWORD *)CompletionContext[50];
  if ( v3 == v1 )
    return;
  v4 = v3 - 2;
  if ( *((_DWORD *)v3 + 19) || *((_DWORD *)v4 + 24) )
    return;
  if ( (_QWORD *)v3[1] != v1 )
    goto LABEL_18;
  v5 = *v3;
  if ( *(_QWORD **)(*v3 + 8LL) != v3 )
    goto LABEL_18;
  *v1 = v5;
  *(_QWORD *)(v5 + 8) = v1;
  if ( !*((_DWORD *)v4 + 22) )
  {
    if ( !*((_BYTE *)v4 + 129) )
    {
LABEL_13:
      ReleaseWsaBufArray(CompletionContext, v4[6]);
      ReleaseApplicationBuffer(CompletionContext, v4);
      goto LABEL_14;
    }
    v6 = (_DWORD *)v4[6];
    if ( !(unsigned int)UseRdma((unsigned int)*v6) )
    {
      RtlFreeHeap(SockPrivateHeap, 0, v7);
      goto LABEL_12;
    }
    v8 = CompletionContext + 112;
    v9 = CompletionContext[112];
    if ( *(_QWORD **)(v9 + 8) == CompletionContext + 112 )
    {
      v10 = v7 - 24;
      *(_QWORD *)v10 = v9;
      *((_QWORD *)v10 + 1) = v8;
      *(_QWORD *)(v9 + 8) = v7 - 24;
      *v8 = v7 - 24;
LABEL_12:
      *((_DWORD *)CompletionContext + 32) -= *v6;
      goto LABEL_13;
    }
LABEL_18:
    __fastfail(3u);
  }
LABEL_14:
  if ( *((_DWORD *)CompletionContext + 44) == 1 || *((_BYTE *)CompletionContext + 208) )
    CheckForSocketDuplicationProtocol((char *)CompletionContext);
}

```

## disassembly

```asm
0x180023cc0  mov     [rsp+arg_0], rbx
0x180023cc5  mov     [rsp+arg_8], rsi
0x180023cca  push    rdi
0x180023ccb  sub     rsp, 20h
0x180023ccf  lea     rax, [rcx+190h]
0x180023cd6  mov     rbx, rcx
0x180023cd9  mov     rcx, [rax]
0x180023cdc  cmp     rcx, rax
0x180023cdf  jz      loc_180023DAF
0x180023ce5  lea     rdi, [rcx-10h]
0x180023ce9  cmp     dword ptr [rdi+5Ch], 0
0x180023ced  jnz     loc_180023DAF
0x180023cf3  cmp     dword ptr [rdi+60h], 0
0x180023cf7  jnz     loc_180023DAF
0x180023cfd  cmp     [rcx+8], rax
0x180023d01  jnz     loc_180023DC0
0x180023d07  mov     rdx, [rcx]
0x180023d0a  cmp     [rdx+8], rcx
0x180023d0e  jnz     loc_180023DC0
0x180023d14  mov     [rax], rdx
0x180023d17  mov     [rdx+8], rax
0x180023d1b  cmp     dword ptr [rdi+58h], 0
0x180023d1f  jnz     short loc_180023D95
0x180023d21  cmp     byte ptr [rdi+81h], 0
0x180023d28  jz      short loc_180023D7E
0x180023d2a  mov     rsi, [rdi+30h]
0x180023d2e  mov     r8, [rsi+8]
0x180023d32  mov     ecx, [rsi]
0x180023d34  call    UseRdma
0x180023d39  test    eax, eax
0x180023d3b  jz      short loc_180023D61
0x180023d3d  lea     rcx, [rbx+380h]
0x180023d44  mov     rdx, [rcx]
0x180023d47  cmp     [rdx+8], rcx
0x180023d4b  jnz     short loc_180023DC0
0x180023d4d  lea     rax, [r8-18h]
0x180023d51  mov     [rax], rdx
0x180023d54  mov     [rax+8], rcx
0x180023d58  mov     [rdx+8], rax
0x180023d5c  mov     [rcx], rax
0x180023d5f  jmp     short loc_180023D76
0x180023d61  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180023d68  xor     edx, edx; Flags
0x180023d6a  call    cs:__imp_RtlFreeHeap
0x180023d71  nop     dword ptr [rax+rax+00h]
0x180023d76  mov     eax, [rsi]
0x180023d78  sub     [rbx+80h], eax
0x180023d7e  mov     rdx, [rdi+30h]
0x180023d82  mov     rcx, rbx
0x180023d85  call    ReleaseWsaBufArray
0x180023d8a  mov     rdx, rdi
0x180023d8d  mov     rcx, rbx
0x180023d90  call    ReleaseApplicationBuffer
0x180023d95  cmp     dword ptr [rbx+0B0h], 1
0x180023d9c  jz      short loc_180023DA7
0x180023d9e  cmp     byte ptr [rbx+0D0h], 0
0x180023da5  jz      short loc_180023DAF
0x180023da7  mov     rcx, rbx; CompletionContext
0x180023daa  call    CheckForSocketDuplicationProtocol
0x180023daf  mov     rbx, [rsp+28h+arg_0]
0x180023db4  mov     rsi, [rsp+28h+arg_8]
0x180023db9  add     rsp, 20h
0x180023dbd  pop     rdi
0x180023dbe  retn
0x180023dc0  mov     ecx, 3
0x180023dc5  int     29h; Win8: RtlFailFast(ecx)
```
