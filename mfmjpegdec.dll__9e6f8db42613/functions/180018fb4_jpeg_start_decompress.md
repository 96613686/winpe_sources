# jpeg_start_decompress

- ea: `0x180018fb4`
- end: `0x180019083`
- name: `jpeg_start_decompress`
- size: `207`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001ff0c`
- `0x1800206fc`

## callees

- `0x180018fb4`
- `0x18001908c`
- `0x180019b48`
- `0x180070010`

## pseudocode

```c
char __fastcall jpeg_start_decompress(__int64 a1)
{
  __int64 v2; // rax

  if ( *(_DWORD *)(a1 + 36) == 202 )
  {
    v2 = *(_QWORD *)(a1 + 512);
    *(_QWORD *)v2 = prepare_for_output_pass;
    *(_QWORD *)(v2 + 8) = finish_output_pass;
    *(_BYTE *)(v2 + 16) = 0;
    *(_BYTE *)(v2 + 108) = 0;
    master_selection(a1);
    if ( *(_BYTE *)(a1 + 88) )
    {
      *(_DWORD *)(a1 + 36) = 207;
      return 1;
    }
    *(_DWORD *)(a1 + 36) = 203;
  }
  else if ( *(_DWORD *)(a1 + 36) != 203 )
  {
    if ( *(_DWORD *)(a1 + 36) != 204 )
    {
      *(_DWORD *)(*(_QWORD *)a1 + 40LL) = 20;
      *(_DWORD *)(*(_QWORD *)a1 + 44LL) = *(_DWORD *)(a1 + 36);
      (**(void (__fastcall ***)(__int64))a1)(a1);
    }
    return output_pass_setup(a1);
  }
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 544) + 32LL) )
  {
    *(_DWORD *)(*(_QWORD *)a1 + 40LL) = 48;
    (**(void (__fastcall ***)(__int64))a1)(a1);
  }
  *(_DWORD *)(a1 + 164) = *(_DWORD *)(a1 + 156);
  return output_pass_setup(a1);
}

```

## disassembly

```asm
0x180018fb4  push    rbx
0x180018fb6  sub     rsp, 20h
0x180018fba  cmp     dword ptr [rcx+24h], 0CAh
0x180018fc1  mov     rbx, rcx
0x180018fc4  jnz     short loc_180019010
0x180018fc6  mov     rax, [rcx+200h]
0x180018fcd  lea     rcx, prepare_for_output_pass
0x180018fd4  mov     [rax], rcx
0x180018fd7  lea     rcx, finish_output_pass
0x180018fde  mov     [rax+8], rcx
0x180018fe2  mov     rcx, rbx
0x180018fe5  mov     byte ptr [rax+10h], 0
0x180018fe9  mov     byte ptr [rax+6Ch], 0
0x180018fed  call    master_selection
0x180018ff2  cmp     byte ptr [rbx+58h], 0
0x180018ff6  jz      short loc_180019007
0x180018ff8  mov     dword ptr [rbx+24h], 0CFh
0x180018fff  mov     al, 1
0x180019001  add     rsp, 20h
0x180019005  pop     rbx
0x180019006  retn
0x180019007  mov     dword ptr [rbx+24h], 0CBh
0x18001900e  jmp     short loc_180019019
0x180019010  cmp     dword ptr [rcx+24h], 0CBh
0x180019017  jnz     short loc_18001904C
0x180019019  mov     rax, [rbx+220h]
0x180019020  cmp     byte ptr [rax+20h], 0
0x180019024  jz      short loc_18001903E
0x180019026  mov     rax, [rbx]
0x180019029  mov     rcx, rbx
0x18001902c  mov     dword ptr [rax+28h], 30h ; '0'
0x180019033  mov     rax, [rbx]
0x180019036  mov     rax, [rax]
0x180019039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001903e  mov     eax, [rbx+9Ch]
0x180019044  mov     [rbx+0A4h], eax
0x18001904a  jmp     short loc_180019076
0x18001904c  cmp     dword ptr [rcx+24h], 0CCh
0x180019053  jz      short loc_180019076
0x180019055  mov     rax, [rcx]
0x180019058  mov     dword ptr [rax+28h], 14h
0x18001905f  mov     rcx, [rcx]
0x180019062  mov     eax, [rbx+24h]
0x180019065  mov     [rcx+2Ch], eax
0x180019068  mov     rcx, rbx
0x18001906b  mov     rax, [rbx]
0x18001906e  mov     rax, [rax]
0x180019071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019076  mov     rcx, rbx
0x180019079  add     rsp, 20h
0x18001907d  pop     rbx
0x18001907e  jmp     output_pass_setup
```
