# DetourDetach

- ea: `0x140002790`
- end: `0x140002904`
- name: `DetourDetach`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000d4f0`

## callees

- `0x1400026d0`
- `0x140002790`
- `0x1400038cc`
- `0x140003978`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400027a0`
- `KERNEL32!GetCurrentThreadId` at `0x1400027a0`
- `KERNEL32!VirtualProtect` at `0x14000287d`
- `KERNEL32!VirtualProtect` at `0x14000287d`
- `KERNEL32!GetLastError` at `0x140002887`
- `KERNEL32!GetLastError` at `0x140002887`

## pseudocode

```c
__int64 __fastcall DetourDetach(_QWORD *a1, __int64 a2)
{
  __int64 result; // rax
  _DWORD *v5; // rbx
  DWORD LastError; // edi
  __int64 v7; // rdi
  __int64 v8; // rax
  unsigned __int64 v9; // rcx
  SIZE_T v10; // rdx
  void *v11; // rbp
  DWORD flOldProtect; // [rsp+40h] [rbp+18h] BYREF

  if ( dword_140017728 != GetCurrentThreadId() )
    return 4317;
  result = (unsigned int)dword_14001772C;
  if ( !dword_14001772C )
  {
    if ( !a2 )
      return 87;
    if ( !a1 )
      return 6;
    if ( !*a1 )
    {
      dword_14001772C = 6;
      qword_140017730 = (__int64)a1;
      return 6;
    }
    v5 = operator new(0x30u);
    if ( v5 )
    {
      v7 = DetourCodeFromPointer(*a1, 0);
      v8 = DetourCodeFromPointer(a2, 0);
      v9 = *(unsigned __int8 *)(v7 + 62);
      if ( (_BYTE)v9 && (v10 = *(unsigned __int8 *)(v7 + 62), v9 <= 0x1E) && *(_QWORD *)(v7 + 80) == v8 )
      {
        v11 = (void *)(*(_QWORD *)(v7 + 72) - v9);
        flOldProtect = 0;
        if ( VirtualProtect(v11, v10, 0x40u, &flOldProtect) )
        {
          v5[2] = 1;
          *((_QWORD *)v5 + 2) = a1;
          *((_QWORD *)v5 + 4) = v7;
          *((_QWORD *)v5 + 3) = v11;
          v5[10] = flOldProtect;
          *(_QWORD *)v5 = qword_140017740;
          result = 0;
          qword_140017740 = v5;
          return result;
        }
        LastError = GetLastError();
      }
      else
      {
        LastError = 9;
        if ( dword_140017720 )
          goto LABEL_20;
      }
    }
    else
    {
      LastError = 8;
    }
    dword_14001772C = LastError;
    if ( !v5 )
    {
LABEL_21:
      qword_140017730 = (__int64)a1;
      return LastError;
    }
LABEL_20:
    operator delete(v5, 0x30u);
    goto LABEL_21;
  }
  return result;
}

```

## disassembly

```asm
0x140002790  mov     [rsp+arg_18], rbp
0x140002795  push    rsi
0x140002796  sub     rsp, 20h
0x14000279a  mov     rbp, rdx
0x14000279d  mov     rsi, rcx
0x1400027a0  call    cs:__imp_GetCurrentThreadId
0x1400027a6  cmp     cs:dword_140017728, eax
0x1400027ac  jz      short loc_1400027BE
0x1400027ae  mov     eax, 10DDh
0x1400027b3  mov     rbp, [rsp+28h+arg_18]
0x1400027b8  add     rsp, 20h
0x1400027bc  pop     rsi
0x1400027bd  retn
0x1400027be  mov     eax, cs:dword_14001772C
0x1400027c4  test    eax, eax
0x1400027c6  jnz     loc_1400028F9
0x1400027cc  test    rbp, rbp
0x1400027cf  jnz     short loc_1400027E1
0x1400027d1  mov     eax, 57h ; 'W'
0x1400027d6  mov     rbp, [rsp+28h+arg_18]
0x1400027db  add     rsp, 20h
0x1400027df  pop     rsi
0x1400027e0  retn
0x1400027e1  test    rsi, rsi
0x1400027e4  jz      short loc_1400027FD
0x1400027e6  cmp     qword ptr [rsi], 0
0x1400027ea  jnz     short loc_14000280D
0x1400027ec  mov     cs:dword_14001772C, 6
0x1400027f6  mov     cs:qword_140017730, rsi
0x1400027fd  mov     eax, 6
0x140002802  mov     rbp, [rsp+28h+arg_18]
0x140002807  add     rsp, 20h
0x14000280b  pop     rsi
0x14000280c  retn
0x14000280d  mov     [rsp+28h+arg_0], rbx
0x140002812  mov     ecx, 30h ; '0'; dwBytes
0x140002817  mov     [rsp+28h+arg_8], rdi
0x14000281c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140002821  mov     rbx, rax
0x140002824  test    rax, rax
0x140002827  jnz     short loc_140002833
0x140002829  mov     edi, 8
0x14000282e  jmp     loc_1400028CE
0x140002833  mov     rcx, [rsi]
0x140002836  xor     edx, edx
0x140002838  call    DetourCodeFromPointer
0x14000283d  xor     edx, edx
0x14000283f  mov     rcx, rbp
0x140002842  mov     rdi, rax
0x140002845  call    DetourCodeFromPointer
0x14000284a  movzx   ecx, byte ptr [rdi+3Eh]
0x14000284e  test    cl, cl
0x140002850  jz      short loc_1400028C0
0x140002852  mov     edx, ecx; dwSize
0x140002854  cmp     rcx, 1Eh
0x140002858  ja      short loc_1400028C0
0x14000285a  cmp     [rdi+50h], rax
0x14000285e  jnz     short loc_1400028C0
0x140002860  mov     rbp, [rdi+48h]
0x140002864  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x140002869  sub     rbp, rcx
0x14000286c  mov     [rsp+28h+flOldProtect], 0
0x140002874  mov     rcx, rbp; lpAddress
0x140002877  mov     r8d, 40h ; '@'; flNewProtect
0x14000287d  call    cs:__imp_VirtualProtect
0x140002883  test    eax, eax
0x140002885  jnz     short loc_140002891
0x140002887  call    cs:__imp_GetLastError
0x14000288d  mov     edi, eax
0x14000288f  jmp     short loc_1400028CE
0x140002891  mov     dword ptr [rbx+8], 1
0x140002898  mov     [rbx+10h], rsi
0x14000289c  mov     [rbx+20h], rdi
0x1400028a0  mov     [rbx+18h], rbp
0x1400028a4  mov     eax, [rsp+28h+flOldProtect]
0x1400028a8  mov     [rbx+28h], eax
0x1400028ab  mov     rax, cs:qword_140017740
0x1400028b2  mov     [rbx], rax
0x1400028b5  xor     eax, eax
0x1400028b7  mov     cs:qword_140017740, rbx
0x1400028be  jmp     short loc_1400028EF
0x1400028c0  cmp     cs:dword_140017720, 0
0x1400028c7  mov     edi, 9
0x1400028cc  jnz     short loc_1400028D9
0x1400028ce  mov     cs:dword_14001772C, edi
0x1400028d4  test    rbx, rbx
0x1400028d7  jz      short loc_1400028E6
0x1400028d9  mov     edx, 30h ; '0'; unsigned __int64
0x1400028de  mov     rcx, rbx; void *
0x1400028e1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400028e6  mov     cs:qword_140017730, rsi
0x1400028ed  mov     eax, edi
0x1400028ef  mov     rbx, [rsp+28h+arg_0]
0x1400028f4  mov     rdi, [rsp+28h+arg_8]
0x1400028f9  mov     rbp, [rsp+28h+arg_18]
0x1400028fe  add     rsp, 20h
0x140002902  pop     rsi
0x140002903  retn
```
