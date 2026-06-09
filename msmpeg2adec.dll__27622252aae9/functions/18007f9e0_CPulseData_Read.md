# CPulseData_Read

- ea: `0x18007f9e0`
- end: `0x18007facd`
- name: `CPulseData_Read`
- size: `237`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18007d4e0`
- `0x18007f350`

## callees

- `0x1800363f0`
- `0x18007f9e0`

## pseudocode

```c
char __fastcall CPulseData_Read(int *a1, _BYTE *a2)
{
  int v4; // eax
  int v5; // esi
  __int64 v6; // rbp

  if ( !*a1 )
    FillBitCache(a1, 1u);
  LOBYTE(v4) = ((unsigned int)a1[1] >> --*a1) & 1;
  *a2 = v4;
  if ( (_BYTE)v4 )
  {
    if ( (unsigned int)*a1 < 2 )
      FillBitCache(a1, 2u);
    *a1 -= 2;
    a2[1] = ((unsigned int)a1[1] >> *a1) & 3;
    if ( (unsigned int)*a1 < 6 )
      FillBitCache(a1, 6u);
    *a1 -= 6;
    v5 = 0;
    LOBYTE(v4) = ((unsigned int)a1[1] >> *a1) & 0x3F;
    a2[2] = v4;
    if ( (char)a2[1] >= 0 )
    {
      do
      {
        if ( (unsigned int)*a1 < 5 )
          FillBitCache(a1, 5u);
        *a1 -= 5;
        v6 = v5;
        a2[v5 + 3] = ((unsigned int)a1[1] >> *a1) & 0x1F;
        if ( (unsigned int)*a1 < 4 )
          FillBitCache(a1, 4u);
        *a1 -= 4;
        ++v5;
        a2[v6 + 7] = ((unsigned int)a1[1] >> *a1) & 0xF;
        v4 = (char)a2[1];
      }
      while ( v5 <= v4 );
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18007f9e0  mov     [rsp+arg_10], rbx
0x18007f9e5  push    rdi
0x18007f9e6  sub     rsp, 20h
0x18007f9ea  cmp     dword ptr [rcx], 1
0x18007f9ed  mov     rdi, rdx
0x18007f9f0  mov     rbx, rcx
0x18007f9f3  jnb     short loc_18007F9FF
0x18007f9f5  mov     edx, 1
0x18007f9fa  call    FillBitCache
0x18007f9ff  dec     dword ptr [rbx]
0x18007fa01  mov     eax, [rbx+4]
0x18007fa04  mov     ecx, [rbx]
0x18007fa06  shr     eax, cl
0x18007fa08  and     al, 1
0x18007fa0a  mov     [rdi], al
0x18007fa0c  jz      loc_18007FAC1
0x18007fa12  cmp     dword ptr [rbx], 2
0x18007fa15  mov     [rsp+28h+arg_8], rsi
0x18007fa1a  jnb     short loc_18007FA29
0x18007fa1c  mov     edx, 2
0x18007fa21  mov     rcx, rbx
0x18007fa24  call    FillBitCache
0x18007fa29  add     dword ptr [rbx], 0FFFFFFFEh
0x18007fa2c  mov     eax, [rbx+4]
0x18007fa2f  mov     ecx, [rbx]
0x18007fa31  shr     eax, cl
0x18007fa33  and     al, 3
0x18007fa35  mov     [rdi+1], al
0x18007fa38  cmp     dword ptr [rbx], 6
0x18007fa3b  jnb     short loc_18007FA4A
0x18007fa3d  mov     edx, 6
0x18007fa42  mov     rcx, rbx
0x18007fa45  call    FillBitCache
0x18007fa4a  add     dword ptr [rbx], 0FFFFFFFAh
0x18007fa4d  xor     esi, esi
0x18007fa4f  mov     eax, [rbx+4]
0x18007fa52  mov     ecx, [rbx]
0x18007fa54  shr     eax, cl
0x18007fa56  and     al, 3Fh
0x18007fa58  mov     [rdi+2], al
0x18007fa5b  cmp     [rdi+1], sil
0x18007fa5f  jl      short loc_18007FABC
0x18007fa61  mov     [rsp+28h+arg_0], rbp
0x18007fa66  cmp     dword ptr [rbx], 5
0x18007fa69  jnb     short loc_18007FA78
0x18007fa6b  mov     edx, 5
0x18007fa70  mov     rcx, rbx
0x18007fa73  call    FillBitCache
0x18007fa78  add     dword ptr [rbx], 0FFFFFFFBh
0x18007fa7b  mov     eax, [rbx+4]
0x18007fa7e  mov     ecx, [rbx]
0x18007fa80  shr     eax, cl
0x18007fa82  and     al, 1Fh
0x18007fa84  movsxd  rbp, esi
0x18007fa87  mov     [rbp+rdi+3], al
0x18007fa8b  cmp     dword ptr [rbx], 4
0x18007fa8e  jnb     short loc_18007FA9D
0x18007fa90  mov     edx, 4
0x18007fa95  mov     rcx, rbx
0x18007fa98  call    FillBitCache
0x18007fa9d  add     dword ptr [rbx], 0FFFFFFFCh
0x18007faa0  inc     esi
0x18007faa2  mov     eax, [rbx+4]
0x18007faa5  mov     ecx, [rbx]
0x18007faa7  shr     eax, cl
0x18007faa9  and     al, 0Fh
0x18007faab  mov     [rbp+rdi+7], al
0x18007faaf  movsx   eax, byte ptr [rdi+1]
0x18007fab3  cmp     esi, eax
0x18007fab5  jle     short loc_18007FA66
0x18007fab7  mov     rbp, [rsp+28h+arg_0]
0x18007fabc  mov     rsi, [rsp+28h+arg_8]
0x18007fac1  mov     rbx, [rsp+28h+arg_10]
0x18007fac6  add     rsp, 20h
0x18007faca  pop     rdi
0x18007facb  retn
```
