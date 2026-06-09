# ConvertCLSIDToString

- ea: `0x180006044`
- end: `0x1800060cc`
- name: `ConvertCLSIDToString`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008118`

## callees

- `0x180006044`

## pseudocode

```c
__int64 __fastcall ConvertCLSIDToString(__int64 a1, _BYTE *a2, _DWORD *a3)
{
  __int64 result; // rax
  _BYTE *v6; // r8
  unsigned int i; // r9d
  __int64 v8; // rcx

  if ( *a3 >= 0x27u )
  {
    *a2 = 123;
    v6 = a2 + 1;
    for ( i = 0; i < 0x14; ++i )
    {
      v8 = *((unsigned __int8 *)qword_18001BEB0 + (int)i);
      if ( (_BYTE)v8 == 45 )
      {
        *v6 = 45;
      }
      else
      {
        *v6 = a0123456789abcd[(unsigned __int64)*(unsigned __int8 *)(v8 + a1) >> 4];
        *++v6 = a0123456789abcd[*(_BYTE *)(v8 + a1) & 0xF];
      }
      ++v6;
    }
    *(_WORD *)v6 = 125;
    result = 0;
  }
  else
  {
    result = 2147942522LL;
  }
  *a3 = 39;
  return result;
}

```

## disassembly

```asm
0x180006044  mov     [rsp+arg_0], rbx
0x180006049  cmp     dword ptr [r8], 27h ; '''
0x18000604d  mov     r10, r8
0x180006050  mov     r11, rcx
0x180006053  jnb     short loc_18000605C
0x180006055  mov     eax, 8007007Ah
0x18000605a  jmp     short loc_1800060BF
0x18000605c  mov     byte ptr [rdx], 7Bh ; '{'
0x18000605f  lea     r8, [rdx+1]
0x180006063  xor     r9d, r9d
0x180006066  lea     rbx, __ImageBase
0x18000606d  movsxd  rax, r9d
0x180006070  movzx   ecx, byte ptr [rax+rbx+1BEB0h]
0x180006078  cmp     cl, 2Dh ; '-'
0x18000607b  jnz     short loc_180006082
0x18000607d  mov     [r8], cl
0x180006080  jmp     short loc_1800060AB
0x180006082  movzx   eax, byte ptr [rcx+r11]
0x180006087  shr     rax, 4
0x18000608b  mov     al, [rax+rbx+1BE90h]
0x180006092  mov     [r8], al
0x180006095  movzx   eax, byte ptr [rcx+r11]
0x18000609a  and     eax, 0Fh
0x18000609d  mov     al, [rax+rbx+1BE90h]
0x1800060a4  mov     [r8+1], al
0x1800060a8  inc     r8
0x1800060ab  inc     r8
0x1800060ae  inc     r9d
0x1800060b1  cmp     r9d, 14h
0x1800060b5  jb      short loc_18000606D
0x1800060b7  mov     word ptr [r8], 7Dh ; '}'
0x1800060bd  xor     eax, eax
0x1800060bf  mov     rbx, [rsp+arg_0]
0x1800060c4  mov     dword ptr [r10], 27h ; '''
0x1800060cb  retn
```
