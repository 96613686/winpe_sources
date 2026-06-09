# QosLineUpdateStats

- ea: `0x14000bc84`
- end: `0x14000bcab`
- name: `QosLineUpdateStats`
- size: `39`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140003ab0`
- `0x140005578`

## callees

- `0x14000bc84`

## pseudocode

```c
__int64 __fastcall QosLineUpdateStats(_DWORD *a1, unsigned int *a2)
{
  __int64 result; // rax
  unsigned int v3; // edx

  result = *a2;
  a1[6] += result;
  v3 = a1[6];
  if ( (int)result <= 0 )
  {
    if ( (_DWORD)result )
      ++a1[16];
    else
      ++a1[18];
  }
  else
  {
    result = (unsigned int)a1[20];
    if ( (unsigned int)result <= v3 )
      result = v3;
    ++a1[15];
    a1[20] = result;
  }
  return result;
}

```

## disassembly

```asm
0x14000bc84  mov     eax, [rdx]
0x14000bc86  add     [rcx+18h], eax
0x14000bc89  mov     edx, [rcx+18h]
0x14000bc8c  test    eax, eax
0x14000bc8e  jle     short loc_14000BCA0
0x14000bc90  mov     eax, [rcx+50h]
0x14000bc93  cmp     eax, edx
0x14000bc95  cmovbe  eax, edx
0x14000bc98  inc     dword ptr [rcx+3Ch]
0x14000bc9b  mov     [rcx+50h], eax
0x14000bc9e  retn
0x14000bca0  jnz     short loc_14000BCA7
0x14000bca2  inc     dword ptr [rcx+48h]
0x14000bca5  retn
0x14000bca7  inc     dword ptr [rcx+40h]
0x14000bcaa  retn
```
