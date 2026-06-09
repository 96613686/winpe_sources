# HandleCompletedSend

- ea: `0x18003f158`
- end: `0x18003f283`
- name: `HandleCompletedSend`
- size: `299`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800475c0`
- `0x18004a520`

## callees

- `0x180024dd4`
- `0x18003f158`
- `0x18003f28c`
- `0x18003f2e0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18003f24c`
- `ntdll!RtlFreeHeap` at `0x18003f24c`

## pseudocode

```c
_QWORD *__fastcall HandleCompletedSend(__int64 a1)
{
  _QWORD *result; // rax
  __int64 v2; // r8
  _QWORD *v3; // rdx
  __int64 v4; // rbx
  __int64 v5; // rdi
  __int64 v6; // rcx
  _QWORD *v7; // rdx
  _QWORD *v8; // rdx
  _DWORD *v9; // rsi
  char *v10; // r8
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  char *v13; // rax

  result = (_QWORD *)(a1 + 40);
  *(_BYTE *)(a1 + 84) = 0;
  v2 = *(_QWORD *)(a1 + 40);
  if ( *(_QWORD *)(v2 + 8) != a1 + 40 )
    goto LABEL_18;
  v3 = *(_QWORD **)(a1 + 48);
  if ( (_QWORD *)*v3 != result )
    goto LABEL_18;
  v4 = *(_QWORD *)(a1 + 72);
  v5 = *(_QWORD *)(a1 + 56);
  *v3 = v2;
  *(_QWORD *)(v2 + 8) = v3;
  v6 = v5 + 368;
  if ( !v4 )
  {
    v7 = *(_QWORD **)(v5 + 376);
    if ( *v7 == v6 )
    {
      *result = v6;
      result[1] = v7;
      *v7 = result;
      *(_QWORD *)(v5 + 376) = result;
      return result;
    }
LABEL_18:
    __fastfail(3u);
  }
  --*(_DWORD *)(v4 + 88);
  v8 = *(_QWORD **)(v5 + 376);
  if ( *v8 != v6 )
    goto LABEL_18;
  *result = v6;
  result[1] = v8;
  *v8 = result;
  *(_QWORD *)(v5 + 376) = result;
  if ( !*(_DWORD *)(v4 + 88) && !*(_DWORD *)(v4 + 92) && !*(_DWORD *)(v4 + 96) )
  {
    if ( *(_BYTE *)(v4 + 129) )
    {
      v9 = *(_DWORD **)(v4 + 48);
      if ( (unsigned int)UseRdma((unsigned int)*v9) )
      {
        v11 = (_QWORD *)(v5 + 896);
        v12 = *(_QWORD *)(v5 + 896);
        if ( *(_QWORD *)(v12 + 8) != v5 + 896 )
          goto LABEL_18;
        v13 = v10 - 24;
        *(_QWORD *)v13 = v12;
        *((_QWORD *)v13 + 1) = v11;
        *(_QWORD *)(v12 + 8) = v10 - 24;
        *v11 = v10 - 24;
      }
      else
      {
        RtlFreeHeap(SockPrivateHeap, 0, v10);
      }
      *(_DWORD *)(v5 + 128) -= *v9;
    }
    ReleaseWsaBufArray(v5, *(_QWORD *)(v4 + 48));
    return (_QWORD *)ReleaseApplicationBuffer(v5, v4);
  }
  return result;
}

```

## disassembly

```asm
0x18003f158  mov     [rsp+arg_0], rbx
0x18003f15d  mov     [rsp+arg_8], rsi
0x18003f162  push    rdi
0x18003f163  sub     rsp, 20h
0x18003f167  xor     r9d, r9d
0x18003f16a  lea     rax, [rcx+28h]
0x18003f16e  mov     [rcx+54h], r9b
0x18003f172  mov     r8, [rax]
0x18003f175  cmp     [r8+8], rax
0x18003f179  jnz     loc_18003F27C
0x18003f17f  mov     rdx, [rax+8]
0x18003f183  cmp     [rdx], rax
0x18003f186  jnz     loc_18003F27C
0x18003f18c  mov     rbx, [rcx+48h]
0x18003f190  mov     rdi, [rcx+38h]
0x18003f194  mov     [rdx], r8
0x18003f197  mov     [r8+8], rdx
0x18003f19b  lea     rcx, [rdi+170h]
0x18003f1a2  test    rbx, rbx
0x18003f1a5  jnz     short loc_18003F1D3
0x18003f1a7  mov     rdx, [rcx+8]
0x18003f1ab  cmp     [rdx], rcx
0x18003f1ae  jnz     loc_18003F27C
0x18003f1b4  mov     [rax], rcx
0x18003f1b7  mov     [rax+8], rdx
0x18003f1bb  mov     [rdx], rax
0x18003f1be  mov     [rcx+8], rax
0x18003f1c2  mov     rbx, [rsp+28h+arg_0]
0x18003f1c7  mov     rsi, [rsp+28h+arg_8]
0x18003f1cc  add     rsp, 20h
0x18003f1d0  pop     rdi
0x18003f1d1  retn
0x18003f1d3  dec     dword ptr [rbx+58h]
0x18003f1d6  mov     rdx, [rcx+8]
0x18003f1da  cmp     [rdx], rcx
0x18003f1dd  jnz     loc_18003F27C
0x18003f1e3  mov     [rax], rcx
0x18003f1e6  mov     [rax+8], rdx
0x18003f1ea  mov     [rdx], rax
0x18003f1ed  mov     [rcx+8], rax
0x18003f1f1  cmp     [rbx+58h], r9d
0x18003f1f5  jnz     short loc_18003F1C2
0x18003f1f7  cmp     [rbx+5Ch], r9d
0x18003f1fb  jnz     short loc_18003F1C2
0x18003f1fd  cmp     [rbx+60h], r9d
0x18003f201  jnz     short loc_18003F1C2
0x18003f203  cmp     [rbx+81h], r9b
0x18003f20a  jz      short loc_18003F260
0x18003f20c  mov     rsi, [rbx+30h]
0x18003f210  mov     r8, [rsi+8]
0x18003f214  mov     ecx, [rsi]
0x18003f216  call    UseRdma
0x18003f21b  test    eax, eax
0x18003f21d  jz      short loc_18003F243
0x18003f21f  lea     rcx, [rdi+380h]
0x18003f226  mov     rdx, [rcx]
0x18003f229  cmp     [rdx+8], rcx
0x18003f22d  jnz     short loc_18003F27C
0x18003f22f  lea     rax, [r8-18h]
0x18003f233  mov     [rax], rdx
0x18003f236  mov     [rax+8], rcx
0x18003f23a  mov     [rdx+8], rax
0x18003f23e  mov     [rcx], rax
0x18003f241  jmp     short loc_18003F258
0x18003f243  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18003f24a  xor     edx, edx; Flags
0x18003f24c  call    cs:__imp_RtlFreeHeap
0x18003f253  nop     dword ptr [rax+rax+00h]
0x18003f258  mov     eax, [rsi]
0x18003f25a  sub     [rdi+80h], eax
0x18003f260  mov     rdx, [rbx+30h]
0x18003f264  mov     rcx, rdi
0x18003f267  call    ReleaseWsaBufArray
0x18003f26c  mov     rdx, rbx
0x18003f26f  mov     rcx, rdi
0x18003f272  call    ReleaseApplicationBuffer
0x18003f277  jmp     loc_18003F1C2
0x18003f27c  mov     ecx, 3
0x18003f281  int     29h; Win8: RtlFailFast(ecx)
```
