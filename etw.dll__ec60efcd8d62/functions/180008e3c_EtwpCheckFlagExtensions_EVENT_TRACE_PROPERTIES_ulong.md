# EtwpCheckFlagExtensions(_EVENT_TRACE_PROPERTIES *,ulong *)

- ea: `0x180008e3c`
- end: `0x180008f28`
- name: `?EtwpCheckFlagExtensions@@YAKPEAU_EVENT_TRACE_PROPERTIES@@PEAK@Z`
- size: `236`
- prototype: `unsigned int __fastcall(struct _EVENT_TRACE_PROPERTIES *, unsigned int *)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800099c0`
- `0x18000a300`
- `0x18000c4a0`
- `0x18000cca0`

## callees

- `0x180008e3c`

## pseudocode

```c
__int64 __fastcall EtwpCheckFlagExtensions(struct _EVENT_TRACE_PROPERTIES *a1, unsigned int *a2)
{
  __int64 v2; // r8
  __int64 BufferSize; // rax
  unsigned int EnableFlags_low; // r9d
  __int64 v5; // r10
  int v6; // r9d
  ULONG *p_ProviderId; // r11
  unsigned __int16 v8; // bx
  unsigned __int16 v9; // cx
  unsigned __int16 v10; // r8
  unsigned __int16 *v11; // r11
  unsigned int v12; // ecx
  unsigned int v13; // r8d

  if ( (a1->EnableFlags & 0x80000000) == 0 )
    return 0;
  v2 = BYTE2(a1->EnableFlags);
  if ( (_BYTE)v2 )
  {
    if ( LOWORD(a1->EnableFlags) >= 0x78u )
    {
      BufferSize = a1->Wnode.BufferSize;
      EnableFlags_low = LOWORD(a1->EnableFlags);
      if ( EnableFlags_low <= (unsigned int)BufferSize )
      {
        if ( (_BYTE)v2 == 0xFF )
        {
          if ( (unsigned __int64)(BufferSize - 120) < 4 )
            return 87;
          v5 = LOWORD(a1->EnableFlags);
          v6 = *(unsigned __int16 *)((char *)&a1->Wnode.BufferSize + v5);
          if ( 4 * (unsigned __int64)*(unsigned __int16 *)((char *)&a1->Wnode.BufferSize + v5) > BufferSize - 120 )
            return 87;
          p_ProviderId = &a1->Wnode.ProviderId;
          v8 = 0;
          v9 = *(_WORD *)((char *)&a1->Wnode.BufferSize + v5 + 2);
          v10 = v6 - 1;
          v11 = (unsigned __int16 *)((char *)p_ProviderId + v5);
          if ( v9 )
          {
            while ( v10 && v10 >= *v11 )
            {
              v10 -= *v11;
              ++v8;
              v11 += 2 * *v11;
              if ( v8 >= v9 )
                goto LABEL_12;
            }
            return 87;
          }
LABEL_12:
          if ( v10 )
            return 87;
          v12 = *a2;
          v13 = *a2 + 4 * v6;
        }
        else
        {
          if ( 4 * v2 > (unsigned __int64)((unsigned int)BufferSize - EnableFlags_low) )
            return 87;
          v12 = *a2;
          v13 = *a2 + 4 * (v2 + 2);
        }
        if ( v13 >= v12 )
        {
          *a2 = v13;
          return 0;
        }
        *a2 = -1;
      }
    }
  }
  return 87;
}

```

## disassembly

```asm
0x180008e3c  mov     [rsp+arg_0], rbx
0x180008e41  mov     [rsp+arg_8], rdi
0x180008e46  xor     edi, edi
0x180008e48  cmp     [rcx+48h], edi
0x180008e4b  jge     loc_180008F0E
0x180008e51  movzx   r8d, byte ptr [rcx+4Ah]
0x180008e56  test    r8b, r8b
0x180008e59  jz      loc_180008F21
0x180008e5f  cmp     word ptr [rcx+48h], 78h ; 'x'
0x180008e64  jb      loc_180008F21
0x180008e6a  mov     eax, [rcx]
0x180008e6c  movzx   r9d, word ptr [rcx+48h]
0x180008e71  cmp     r9d, eax
0x180008e74  ja      loc_180008F21
0x180008e7a  cmp     r8b, 0FFh
0x180008e7e  jnz     short loc_180008EEB
0x180008e80  lea     r8, [rax-78h]
0x180008e84  cmp     r8, 4
0x180008e88  jb      loc_180008F21
0x180008e8e  movzx   r10d, word ptr [rcx+48h]
0x180008e93  movzx   r9d, word ptr [r10+rcx]
0x180008e98  mov     eax, r9d
0x180008e9b  shl     rax, 2
0x180008e9f  cmp     rax, r8
0x180008ea2  ja      short loc_180008F21
0x180008ea4  lea     r11, [rcx+4]
0x180008ea8  mov     ebx, edi
0x180008eaa  movzx   ecx, word ptr [r10+rcx+2]
0x180008eb0  lea     r8d, [r9-1]
0x180008eb4  add     r11, r10
0x180008eb7  cmp     di, cx
0x180008eba  jnb     short loc_180008EDD
0x180008ebc  cmp     r8w, 1
0x180008ec1  jb      short loc_180008F21
0x180008ec3  cmp     r8w, [r11]
0x180008ec7  jb      short loc_180008F21
0x180008ec9  sub     r8w, [r11]
0x180008ecd  inc     bx
0x180008ed0  movzx   eax, word ptr [r11]
0x180008ed4  lea     r11, [r11+rax*4]
0x180008ed8  cmp     bx, cx
0x180008edb  jb      short loc_180008EBC
0x180008edd  test    r8w, r8w
0x180008ee1  jnz     short loc_180008F21
0x180008ee3  mov     ecx, [rdx]
0x180008ee5  lea     r8d, [rcx+r9*4]
0x180008ee9  jmp     short loc_180008F06
0x180008eeb  sub     eax, r9d
0x180008eee  mov     ecx, eax
0x180008ef0  mov     rax, r8
0x180008ef3  shl     rax, 2
0x180008ef7  cmp     rax, rcx
0x180008efa  ja      short loc_180008F21
0x180008efc  mov     ecx, [rdx]
0x180008efe  add     r8d, 2
0x180008f02  lea     r8d, [rcx+r8*4]
0x180008f06  cmp     r8d, ecx
0x180008f09  jb      short loc_180008F1B
0x180008f0b  mov     [rdx], r8d
0x180008f0e  xor     eax, eax
0x180008f10  mov     rbx, [rsp+arg_0]
0x180008f15  mov     rdi, [rsp+arg_8]
0x180008f1a  retn
0x180008f1b  mov     dword ptr [rdx], 0FFFFFFFFh
0x180008f21  mov     eax, 57h ; 'W'
0x180008f26  jmp     short loc_180008F10
```
