# SfuCreateDefaultSecurityAttributes

- ea: `0x14000fe8c`
- end: `0x14000ff2e`
- name: `SfuCreateDefaultSecurityAttributes`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400030c0`

## callees

- `0x1400016e2`
- `0x1400016ee`
- `0x14000facc`
- `0x14000fe8c`

## pseudocode

```c
__int64 __fastcall SfuCreateDefaultSecurityAttributes(void **a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v5; // edi
  void *v6; // rax
  __int64 result; // rax
  void *Block; // [rsp+30h] [rbp+8h] BYREF

  Block = 0;
  if ( !a1 )
    return 0;
  v5 = 0;
  if ( !*a1 )
  {
    v6 = malloc_0(0x18u);
    *a1 = v6;
    v5 = 1;
    if ( !v6 )
    {
LABEL_8:
      if ( *a1 )
      {
        free_0(*a1);
        *a1 = 0;
      }
      return 0;
    }
  }
  if ( !(unsigned int)CreateDefaultSecDescEx(&Block, a2, 0, a4) )
  {
    if ( Block )
      free_0(Block);
    if ( !v5 )
      return 0;
    goto LABEL_8;
  }
  result = 1;
  *(_DWORD *)*a1 = 24;
  *((_DWORD *)*a1 + 4) = 0;
  *((_QWORD *)*a1 + 1) = Block;
  return result;
}

```

## disassembly

```asm
0x14000fe8c  mov     [rsp+arg_8], rbx
0x14000fe91  push    rdi
0x14000fe92  sub     rsp, 20h
0x14000fe96  mov     [rsp+28h+Block], 0
0x14000fe9f  mov     rbx, rcx
0x14000fea2  test    rcx, rcx
0x14000fea5  jz      short loc_14000FEFB
0x14000fea7  xor     edi, edi
0x14000fea9  cmp     [rcx], rdi
0x14000feac  jnz     short loc_14000FEC3
0x14000feae  lea     ecx, [rdi+18h]; Size
0x14000feb1  call    malloc_0
0x14000feb6  mov     [rbx], rax
0x14000feb9  mov     edi, 1
0x14000febe  test    rax, rax
0x14000fec1  jz      short loc_14000FEE7
0x14000fec3  xor     r8d, r8d
0x14000fec6  lea     rcx, [rsp+28h+Block]
0x14000fecb  call    CreateDefaultSecDescEx
0x14000fed0  test    eax, eax
0x14000fed2  jnz     short loc_14000FF08
0x14000fed4  mov     rcx, [rsp+28h+Block]; Block
0x14000fed9  test    rcx, rcx
0x14000fedc  jz      short loc_14000FEE3
0x14000fede  call    free_0
0x14000fee3  test    edi, edi
0x14000fee5  jz      short loc_14000FEFB
0x14000fee7  mov     rcx, [rbx]; Block
0x14000feea  test    rcx, rcx
0x14000feed  jz      short loc_14000FEFB
0x14000feef  call    free_0
0x14000fef4  mov     qword ptr [rbx], 0
0x14000fefb  xor     eax, eax
0x14000fefd  mov     rbx, [rsp+28h+arg_8]
0x14000ff02  add     rsp, 20h
0x14000ff06  pop     rdi
0x14000ff07  retn
0x14000ff08  mov     rcx, [rbx]
0x14000ff0b  mov     eax, 1
0x14000ff10  mov     dword ptr [rcx], 18h
0x14000ff16  mov     rcx, [rbx]
0x14000ff19  mov     dword ptr [rcx+10h], 0
0x14000ff20  mov     rdx, [rbx]
0x14000ff23  mov     rcx, [rsp+28h+Block]
0x14000ff28  mov     [rdx+8], rcx
0x14000ff2c  jmp     short loc_14000FEFD
```
