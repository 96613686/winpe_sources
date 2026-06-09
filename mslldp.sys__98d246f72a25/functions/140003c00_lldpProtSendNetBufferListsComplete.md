# lldpProtSendNetBufferListsComplete

- ea: `0x140003c00`
- end: `0x140003cb9`
- name: `lldpProtSendNetBufferListsComplete`
- size: `185`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140003c00`
- `0x140004b00`

## pseudocode

```c
__int64 __fastcall lldpProtSendNetBufferListsComplete(__int64 a1, __int64 *a2)
{
  __int64 *v2; // rbx
  __int64 v3; // r9
  __int64 v4; // rdi
  __int64 *v5; // rsi
  __int64 v6; // rcx
  __int64 result; // rax

  if ( a2 )
  {
    v2 = a2;
    while ( 1 )
    {
      v3 = *((unsigned int *)v2 + 35);
      v4 = v2[8];
      v5 = (__int64 *)*v2;
      if ( (_DWORD)v3 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          result = WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_546502ed7e6b3bd4e6d6388a8a9b5935_Traceguids, v3);
      }
      else
      {
        _InterlockedIncrement64((volatile signed __int64 *)(v4 + 912));
      }
      *v2 = 0;
      if ( v2 == *(__int64 **)(v4 + 160) )
        break;
      if ( v2 == *(__int64 **)(v4 + 192) )
      {
        v6 = 184;
        goto LABEL_10;
      }
LABEL_7:
      v2 = v5;
      if ( !v5 )
        return result;
    }
    v6 = 152;
LABEL_10:
    result = (unsigned int)_InterlockedExchange((volatile __int32 *)(v4 + v6), 0);
    goto LABEL_7;
  }
  return result;
}

```

## disassembly

```asm
0x140003c00  test    rdx, rdx
0x140003c03  jz      short locret_140003C7B
0x140003c05  push    rbx
0x140003c06  sub     rsp, 20h
0x140003c0a  mov     [rsp+28h+arg_0], rbp
0x140003c0f  mov     rbx, rdx
0x140003c12  mov     [rsp+28h+arg_8], rsi
0x140003c17  xor     ebp, ebp
0x140003c19  mov     [rsp+28h+arg_10], rdi
0x140003c1e  mov     [rsp+28h+arg_18], r14
0x140003c23  lea     r14, WPP_GLOBAL_Control
0x140003c2a  mov     r9d, [rbx+8Ch]
0x140003c31  mov     rdi, [rbx+40h]
0x140003c35  mov     rsi, [rbx]
0x140003c38  test    r9d, r9d
0x140003c3b  jnz     short loc_140003C89
0x140003c3d  lock inc qword ptr [rdi+390h]
0x140003c45  mov     [rbx], rbp
0x140003c48  cmp     rbx, [rdi+0A0h]
0x140003c4f  jz      short loc_140003C7D
0x140003c51  cmp     rbx, [rdi+0C0h]
0x140003c58  jz      short loc_140003CB2
0x140003c5a  mov     rbx, rsi
0x140003c5d  test    rsi, rsi
0x140003c60  jnz     short loc_140003C2A
0x140003c62  mov     r14, [rsp+28h+arg_18]
0x140003c67  mov     rdi, [rsp+28h+arg_10]
0x140003c6c  mov     rsi, [rsp+28h+arg_8]
0x140003c71  mov     rbp, [rsp+28h+arg_0]
0x140003c76  add     rsp, 20h
0x140003c7a  pop     rbx
0x140003c7b  retn
0x140003c7d  mov     ecx, 98h
0x140003c82  mov     eax, ebp
0x140003c84  xchg    eax, [rdi+rcx]
0x140003c87  jmp     short loc_140003C5A
0x140003c89  mov     rcx, cs:WPP_GLOBAL_Control
0x140003c90  cmp     rcx, r14
0x140003c93  jz      short loc_140003C45
0x140003c95  cmp     byte ptr [rcx+29h], 3
0x140003c99  jb      short loc_140003C45
0x140003c9b  mov     rcx, [rcx+18h]
0x140003c9f  lea     r8, WPP_546502ed7e6b3bd4e6d6388a8a9b5935_Traceguids
0x140003ca6  mov     edx, 12h
0x140003cab  call    WPP_SF_d
0x140003cb0  jmp     short loc_140003C45
0x140003cb2  mov     ecx, 0B8h
0x140003cb7  jmp     short loc_140003C82
```
