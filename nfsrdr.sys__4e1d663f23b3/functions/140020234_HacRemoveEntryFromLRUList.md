# HacRemoveEntryFromLRUList

- ea: `0x140020234`
- end: `0x140020304`
- name: `HacRemoveEntryFromLRUList`
- size: `208`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140005c90`
- `0x14001fad0`

## callees

- `0x140015a40`
- `0x140020234`

## pseudocode

```c
__int64 __fastcall HacRemoveEntryFromLRUList(_QWORD *a1)
{
  __int64 v1; // rdi
  __int64 result; // rax
  _QWORD *v4; // rdx
  __int64 v5; // rcx

  v1 = a1[5];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids, a1 + 8);
  if ( *(_QWORD **)(v1 + 88) == a1 )
  {
    result = a1[2];
    if ( result )
    {
      *(_QWORD *)(v1 + 88) = result;
      result = a1[2];
      *(_QWORD *)(result + 24) = 0;
    }
    else
    {
      *(_QWORD *)(v1 + 96) = 0;
      *(_QWORD *)(v1 + 88) = 0;
    }
    v4 = a1 + 3;
  }
  else
  {
    v4 = a1 + 3;
    result = a1[3];
    if ( *(_QWORD **)(v1 + 96) == a1 )
    {
      if ( result )
      {
        *(_QWORD *)(v1 + 96) = result;
        result = *v4;
        *(_QWORD *)(*v4 + 16LL) = 0;
      }
    }
    else if ( result )
    {
      v5 = a1[2];
      if ( v5 )
      {
        *(_QWORD *)(result + 16) = v5;
        result = *v4;
        *(_QWORD *)(a1[2] + 24LL) = *v4;
      }
    }
  }
  a1[2] = 0;
  *v4 = 0;
  return result;
}

```

## disassembly

```asm
0x140020234  mov     [rsp+arg_0], rbx
0x140020239  push    rdi
0x14002023a  sub     rsp, 20h
0x14002023e  mov     rdi, [rcx+28h]
0x140020242  mov     rbx, rcx
0x140020245  mov     rcx, cs:WPP_GLOBAL_Control
0x14002024c  lea     rax, WPP_GLOBAL_Control
0x140020253  cmp     rcx, rax
0x140020256  jz      short loc_14002027A
0x140020258  test    dword ptr [rcx+2Ch], 800h
0x14002025f  jz      short loc_14002027A
0x140020261  mov     rcx, [rcx+18h]
0x140020265  lea     r9, [rbx+40h]
0x140020269  mov     edx, 28h ; '('
0x14002026e  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x140020275  call    WPP_SF_Z
0x14002027a  cmp     [rdi+58h], rbx
0x14002027e  jnz     short loc_1400202A9
0x140020280  mov     rax, [rbx+10h]
0x140020284  test    rax, rax
0x140020287  jnz     short loc_140020293
0x140020289  mov     [rdi+60h], rax
0x14002028d  mov     [rdi+58h], rax
0x140020291  jmp     short loc_1400202A3
0x140020293  mov     [rdi+58h], rax
0x140020297  mov     rax, [rbx+10h]
0x14002029b  mov     qword ptr [rax+18h], 0
0x1400202a3  lea     rdx, [rbx+18h]
0x1400202a7  jmp     short loc_1400202E9
0x1400202a9  lea     rdx, [rbx+18h]
0x1400202ad  mov     rax, [rdx]
0x1400202b0  cmp     [rdi+60h], rbx
0x1400202b4  jnz     short loc_1400202CC
0x1400202b6  test    rax, rax
0x1400202b9  jz      short loc_1400202E9
0x1400202bb  mov     [rdi+60h], rax
0x1400202bf  mov     rax, [rdx]
0x1400202c2  mov     qword ptr [rax+10h], 0
0x1400202ca  jmp     short loc_1400202E9
0x1400202cc  test    rax, rax
0x1400202cf  jz      short loc_1400202E9
0x1400202d1  mov     rcx, [rbx+10h]
0x1400202d5  test    rcx, rcx
0x1400202d8  jz      short loc_1400202E9
0x1400202da  mov     [rax+10h], rcx
0x1400202de  mov     rcx, [rbx+10h]
0x1400202e2  mov     rax, [rdx]
0x1400202e5  mov     [rcx+18h], rax
0x1400202e9  mov     qword ptr [rbx+10h], 0
0x1400202f1  mov     rbx, [rsp+28h+arg_0]
0x1400202f6  mov     qword ptr [rdx], 0
0x1400202fd  add     rsp, 20h
0x140020301  pop     rdi
0x140020302  retn
```
