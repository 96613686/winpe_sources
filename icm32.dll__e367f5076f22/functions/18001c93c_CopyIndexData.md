# CopyIndexData

- ea: `0x18001c93c`
- end: `0x18001ca98`
- name: `CopyIndexData`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ee40`

## callees

- `0x18001c93c`

## pseudocode

```c
char __fastcall CopyIndexData(__int64 a1, __int64 *a2, __int64 a3)
{
  __int64 v5; // rdi
  int v6; // r10d
  int v7; // esi
  _BYTE *v8; // rdx
  char result; // al
  _BYTE *v10; // r8
  int i; // ecx
  char *v12; // rdx
  _BYTE *v13; // r8
  char v14; // al
  int j; // r11d
  char *v16; // rdx
  char v17; // al
  int k; // r11d
  _BYTE *v19; // r8
  int m; // r11d
  _BYTE *v21; // rdx

  if ( *(int *)(a1 + 12) > 0 )
  {
    v5 = *a2;
    v6 = 0;
    v7 = *((_DWORD *)a2 + 4);
    do
    {
      v8 = (_BYTE *)(*(_QWORD *)a1 + v6 * *(_DWORD *)(a1 + 16));
      result = v6 * v7;
      v10 = (_BYTE *)(v5 + v6 * v7);
      if ( *(_DWORD *)(a3 + 40) == 24 )
      {
        if ( *(_DWORD *)(a3 + 44) == 24 )
        {
          for ( i = 0; i < *(_DWORD *)(a1 + 8); v10 = v13 + 1 )
          {
            ++i;
            *v10 = *v8;
            v12 = v8 + 1;
            v13 = v10 + 1;
            v14 = *v12++;
            *v13++ = v14;
            result = *v12;
            v8 = v12 + 1;
            *v13 = result;
          }
        }
        else if ( *(_DWORD *)(a3 + 44) == 32 )
        {
          for ( j = 0; j < *(_DWORD *)(a1 + 8); v10 += 4 )
          {
            ++j;
            *v10 = *v8;
            v16 = v8 + 1;
            v17 = *v16++;
            v10[1] = v17;
            result = *v16;
            v8 = v16 + 1;
            v10[2] = result;
          }
        }
      }
      else if ( *(_DWORD *)(a3 + 40) == 32 )
      {
        if ( *(_DWORD *)(a3 + 44) == 24 )
        {
          for ( k = 0; k < *(_DWORD *)(a1 + 8); v10 = v19 + 1 )
          {
            ++k;
            *v10 = *v8;
            v19 = v10 + 1;
            *v19++ = v8[1];
            result = v8[2];
            v8 += 4;
            *v19 = result;
          }
        }
        else if ( *(_DWORD *)(a3 + 44) == 32 )
        {
          for ( m = 0; m < *(_DWORD *)(a1 + 8); v10 += 4 )
          {
            ++m;
            *v10 = *v8;
            v21 = v8 + 1;
            v10[1] = *v21;
            result = v21[1];
            v8 = v21 + 3;
            v10[2] = result;
          }
        }
      }
      ++v6;
    }
    while ( v6 < *(_DWORD *)(a1 + 12) );
  }
  return result;
}

```

## disassembly

```asm
0x18001c93c  push    rbx
0x18001c93e  push    rsi
0x18001c93f  push    rdi
0x18001c940  push    r14
0x18001c942  cmp     dword ptr [rcx+0Ch], 0
0x18001c946  mov     rbx, r8
0x18001c949  mov     r9, rcx
0x18001c94c  jle     loc_18001CA92
0x18001c952  mov     rdi, [rdx]
0x18001c955  xor     r10d, r10d
0x18001c958  mov     esi, [rdx+10h]
0x18001c95b  lea     r14d, [r10+1]
0x18001c95f  mov     eax, [r9+10h]
0x18001c963  imul    eax, r10d
0x18001c967  movsxd  rdx, eax
0x18001c96a  mov     eax, esi
0x18001c96c  add     rdx, [r9]
0x18001c96f  imul    eax, r10d
0x18001c973  movsxd  r8, eax
0x18001c976  add     r8, rdi
0x18001c979  cmp     dword ptr [rbx+28h], 18h
0x18001c97d  jnz     loc_18001CA08
0x18001c983  cmp     dword ptr [rbx+2Ch], 18h
0x18001c987  jnz     short loc_18001C9C4
0x18001c989  xor     ecx, ecx
0x18001c98b  cmp     [r9+8], ecx
0x18001c98f  jle     loc_18001CA85
0x18001c995  mov     al, [rdx]
0x18001c997  add     ecx, r14d
0x18001c99a  mov     [r8], al
0x18001c99d  add     rdx, r14
0x18001c9a0  add     r8, r14
0x18001c9a3  mov     al, [rdx]
0x18001c9a5  add     rdx, r14
0x18001c9a8  mov     [r8], al
0x18001c9ab  add     r8, r14
0x18001c9ae  mov     al, [rdx]
0x18001c9b0  add     rdx, r14
0x18001c9b3  mov     [r8], al
0x18001c9b6  add     r8, r14
0x18001c9b9  cmp     ecx, [r9+8]
0x18001c9bd  jl      short loc_18001C995
0x18001c9bf  jmp     loc_18001CA85
0x18001c9c4  cmp     dword ptr [rbx+2Ch], 20h ; ' '
0x18001c9c8  jnz     loc_18001CA85
0x18001c9ce  xor     r11d, r11d
0x18001c9d1  cmp     [r9+8], r11d
0x18001c9d5  jle     loc_18001CA85
0x18001c9db  mov     al, [rdx]
0x18001c9dd  add     r11d, r14d
0x18001c9e0  mov     [r8], al
0x18001c9e3  add     rdx, r14
0x18001c9e6  mov     al, [rdx]
0x18001c9e8  add     rdx, r14
0x18001c9eb  mov     [r8+r14], al
0x18001c9ef  mov     al, [rdx]
0x18001c9f1  add     rdx, r14
0x18001c9f4  mov     [r8+r14+1], al
0x18001c9f9  add     r8, 3
0x18001c9fd  add     r8, r14
0x18001ca00  cmp     r11d, [r9+8]
0x18001ca04  jl      short loc_18001C9DB
0x18001ca06  jmp     short loc_18001CA85
0x18001ca08  cmp     dword ptr [rbx+28h], 20h ; ' '
0x18001ca0c  jnz     short loc_18001CA85
0x18001ca0e  cmp     dword ptr [rbx+2Ch], 18h
0x18001ca12  jnz     short loc_18001CA4C
0x18001ca14  xor     r11d, r11d
0x18001ca17  cmp     [r9+8], r11d
0x18001ca1b  jle     short loc_18001CA85
0x18001ca1d  mov     al, [rdx]
0x18001ca1f  add     r11d, r14d
0x18001ca22  mov     [r8], al
0x18001ca25  add     r8, r14
0x18001ca28  mov     al, [rdx+r14]
0x18001ca2c  mov     [r8], al
0x18001ca2f  add     r8, r14
0x18001ca32  mov     al, [rdx+r14+1]
0x18001ca37  add     rdx, 3
0x18001ca3b  add     rdx, r14
0x18001ca3e  mov     [r8], al
0x18001ca41  add     r8, r14
0x18001ca44  cmp     r11d, [r9+8]
0x18001ca48  jl      short loc_18001CA1D
0x18001ca4a  jmp     short loc_18001CA85
0x18001ca4c  cmp     dword ptr [rbx+2Ch], 20h ; ' '
0x18001ca50  jnz     short loc_18001CA85
0x18001ca52  xor     r11d, r11d
0x18001ca55  cmp     [r9+8], r11d
0x18001ca59  jle     short loc_18001CA85
0x18001ca5b  mov     al, [rdx]
0x18001ca5d  add     r11d, r14d
0x18001ca60  mov     [r8], al
0x18001ca63  add     rdx, r14
0x18001ca66  mov     al, [rdx]
0x18001ca68  mov     [r8+r14], al
0x18001ca6c  mov     al, [rdx+1]
0x18001ca6f  add     rdx, 3
0x18001ca73  mov     [r8+r14+1], al
0x18001ca78  add     r8, 3
0x18001ca7c  add     r8, r14
0x18001ca7f  cmp     r11d, [r9+8]
0x18001ca83  jl      short loc_18001CA5B
0x18001ca85  add     r10d, r14d
0x18001ca88  cmp     r10d, [r9+0Ch]
0x18001ca8c  jl      loc_18001C95F
0x18001ca92  pop     r14
0x18001ca94  pop     rdi
0x18001ca95  pop     rsi
0x18001ca96  pop     rbx
0x18001ca97  retn
```
