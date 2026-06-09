# FwhcMapEventToDiagError

- ea: `0x18000cff4`
- end: `0x18000d0ff`
- name: `FwhcMapEventToDiagError`
- size: `267`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180008d7c`
- `0x18000b548`
- `0x18000b790`
- `0x18000d108`

## callees

- `0x18000b23c`
- `0x18000b844`
- `0x18000cff4`

## pseudocode

```c
__int64 __fastcall FwhcMapEventToDiagError(__int64 a1, int a2, __int64 a3)
{
  _DWORD *v6; // rdx
  int v7; // r11d
  __int64 **v8; // rcx
  int v9; // edx
  __int64 v10; // rax

  v7 = FwhcCheckPolicyMismatchEvent(a1, a3);
  if ( v7 >= 0 && !*v6 )
  {
    v7 = FwhcCheckAuthFailureEvent(a1, (__int64)v6);
    if ( v7 >= 0 && !*(_DWORD *)a3 )
    {
      v8 = (__int64 **)(a1 + 144);
      if ( *(_DWORD *)(a1 + 136) == 3 )
      {
        v9 = 10;
        v10 = **v8;
      }
      else
      {
        v9 = 0;
        v10 = 0;
      }
      v7 = 0;
      *(_QWORD *)(a3 + 8) = v10;
      *(_DWORD *)a3 = v9;
      if ( !v9 )
      {
        if ( *(_BYTE *)(a3 + 45) || *(_DWORD *)(a1 + 136) > 2u || *(_DWORD *)*v8 != 13805 )
        {
          if ( a2
            && *(_DWORD *)(a1 + 136) <= 2u
            && *(_DWORD *)*v8 != 13805
            && *(_DWORD *)*v8 != 13825
            && *(_DWORD *)*v8 != 13849 )
          {
            *(_QWORD *)(a3 + 8) = (*v8)[7];
            *(_DWORD *)a3 = 16;
            *(_DWORD *)(a3 + 4) = *(_DWORD *)*v8;
          }
        }
        else
        {
          *(_QWORD *)(a3 + 8) = (*v8)[7];
          *(_DWORD *)a3 = 15;
        }
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000cff4  mov     [rsp+arg_0], rbx
0x18000cff9  mov     [rsp+arg_8], rsi
0x18000cffe  push    rdi
0x18000cfff  sub     rsp, 20h
0x18000d003  mov     esi, edx
0x18000d005  mov     rbx, r8
0x18000d008  mov     rdx, r8
0x18000d00b  mov     rdi, rcx
0x18000d00e  call    FwhcCheckPolicyMismatchEvent
0x18000d013  mov     r11d, eax
0x18000d016  test    eax, eax
0x18000d018  js      loc_18000D0EC
0x18000d01e  cmp     dword ptr [rdx], 0
0x18000d021  jnz     loc_18000D0EC
0x18000d027  mov     rcx, rdi
0x18000d02a  call    FwhcCheckAuthFailureEvent
0x18000d02f  mov     r11d, eax
0x18000d032  test    eax, eax
0x18000d034  js      loc_18000D0EC
0x18000d03a  cmp     dword ptr [rbx], 0
0x18000d03d  jnz     loc_18000D0EC
0x18000d043  cmp     dword ptr [rdi+88h], 3
0x18000d04a  lea     rcx, [rdi+90h]
0x18000d051  jz      short loc_18000D059
0x18000d053  xor     edx, edx
0x18000d055  xor     eax, eax
0x18000d057  jmp     short loc_18000D064
0x18000d059  mov     rax, [rcx]
0x18000d05c  mov     edx, 0Ah
0x18000d061  mov     rax, [rax]
0x18000d064  xor     r11d, r11d
0x18000d067  mov     [rbx+8], rax
0x18000d06b  mov     [rbx], edx
0x18000d06d  test    edx, edx
0x18000d06f  jnz     short loc_18000D0EC
0x18000d071  mov     r9d, 35EDh
0x18000d077  cmp     [rbx+2Dh], r11b
0x18000d07b  jnz     short loc_18000D0A9
0x18000d07d  mov     eax, [rdi+88h]
0x18000d083  test    eax, eax
0x18000d085  jnz     short loc_18000D09F
0x18000d087  mov     rax, [rcx]
0x18000d08a  cmp     [rax], r9d
0x18000d08d  jnz     short loc_18000D0A9
0x18000d08f  mov     rax, [rax+38h]
0x18000d093  mov     [rbx+8], rax
0x18000d097  mov     dword ptr [rbx], 0Fh
0x18000d09d  jmp     short loc_18000D0EC
0x18000d09f  cmp     eax, 1
0x18000d0a2  jz      short loc_18000D087
0x18000d0a4  cmp     eax, 2
0x18000d0a7  jz      short loc_18000D087
0x18000d0a9  test    esi, esi
0x18000d0ab  jz      short loc_18000D0EC
0x18000d0ad  mov     eax, [rdi+88h]
0x18000d0b3  test    eax, eax
0x18000d0b5  jz      short loc_18000D0C1
0x18000d0b7  cmp     eax, 1
0x18000d0ba  jz      short loc_18000D0C1
0x18000d0bc  cmp     eax, 2
0x18000d0bf  jnz     short loc_18000D0EC
0x18000d0c1  mov     r8, [rcx]
0x18000d0c4  mov     edx, [r8]
0x18000d0c7  sub     edx, r9d
0x18000d0ca  jz      short loc_18000D0EC
0x18000d0cc  sub     edx, 14h
0x18000d0cf  jz      short loc_18000D0EC
0x18000d0d1  cmp     edx, 18h
0x18000d0d4  jz      short loc_18000D0EC
0x18000d0d6  mov     rax, [r8+38h]
0x18000d0da  mov     [rbx+8], rax
0x18000d0de  mov     dword ptr [rbx], 10h
0x18000d0e4  mov     rax, [rcx]
0x18000d0e7  mov     ecx, [rax]
0x18000d0e9  mov     [rbx+4], ecx
0x18000d0ec  mov     rbx, [rsp+28h+arg_0]
0x18000d0f1  mov     eax, r11d
0x18000d0f4  mov     rsi, [rsp+28h+arg_8]
0x18000d0f9  add     rsp, 20h
0x18000d0fd  pop     rdi
0x18000d0fe  retn
```
