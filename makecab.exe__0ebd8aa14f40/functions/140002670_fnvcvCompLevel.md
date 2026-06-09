# fnvcvCompLevel

- ea: `0x140002670`
- end: `0x1400026ee`
- name: `fnvcvCompLevel`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001b04`
- `0x140002670`

## pseudocode

```c
__int64 __fastcall fnvcvCompLevel(__int64 a1, __int64 a2, const char *a3, _BYTE *a4, int a5, __int64 a6)
{
  const char *v7; // rdi
  __int64 v9; // rcx
  __int64 v10; // rax
  _BYTE *v11; // rax

  v7 = a3;
  if ( (unsigned int)CompLevelFromPSZ(a3, a6) == -1 )
    return 0;
  v9 = a5;
  if ( a5 )
  {
    if ( (unsigned __int64)a5 > 0x7FFFFFFF )
    {
      *a4 = 0;
    }
    else
    {
      v10 = 2147483646;
      do
      {
        if ( !v10 )
          break;
        if ( !*v7 )
          break;
        *a4++ = *v7++;
        --v10;
        --v9;
      }
      while ( v9 );
      v11 = a4 - 1;
      if ( v9 )
        v11 = a4;
      *v11 = 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140002670  mov     [rsp+arg_0], rbx
0x140002675  push    rdi
0x140002676  sub     rsp, 20h
0x14000267a  mov     rdx, [rsp+28h+arg_28]
0x14000267f  mov     rcx, r8
0x140002682  mov     rbx, r9
0x140002685  mov     rdi, r8
0x140002688  call    CompLevelFromPSZ
0x14000268d  cmp     eax, 0FFFFFFFFh
0x140002690  jnz     short loc_140002696
0x140002692  xor     eax, eax
0x140002694  jmp     short loc_1400026E3
0x140002696  movsxd  rax, [rsp+28h+arg_20]
0x14000269b  mov     rcx, rax
0x14000269e  test    eax, eax
0x1400026a0  jz      short loc_1400026DE
0x1400026a2  cmp     rax, 7FFFFFFFh
0x1400026a8  ja      short loc_1400026DB
0x1400026aa  mov     eax, 7FFFFFFEh
0x1400026af  test    rax, rax
0x1400026b2  jz      short loc_1400026CB
0x1400026b4  mov     dl, [rdi]
0x1400026b6  test    dl, dl
0x1400026b8  jz      short loc_1400026CB
0x1400026ba  mov     [rbx], dl
0x1400026bc  inc     rdi
0x1400026bf  inc     rbx
0x1400026c2  dec     rax
0x1400026c5  sub     rcx, 1
0x1400026c9  jnz     short loc_1400026AF
0x1400026cb  test    rcx, rcx
0x1400026ce  lea     rax, [rbx-1]
0x1400026d2  cmovnz  rax, rbx
0x1400026d6  mov     byte ptr [rax], 0
0x1400026d9  jmp     short loc_1400026DE
0x1400026db  mov     byte ptr [rbx], 0
0x1400026de  mov     eax, 1
0x1400026e3  mov     rbx, [rsp+28h+arg_0]
0x1400026e8  add     rsp, 20h
0x1400026ec  pop     rdi
0x1400026ed  retn
```
