# CryptHash::GetHash(uchar *,ulong,ulong *)

- ea: `0x18000409c`
- end: `0x180004102`
- name: `?GetHash@CryptHash@@QEAAKPEAEKPEAK@Z`
- size: `102`
- prototype: `unsigned int(CryptHash *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004108`
- `0x1800042ec`

## callees

- `0x18000409c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800040e1`
- `KERNEL32!GetLastError` at `0x1800040e1`
- `ADVAPI32!CryptGetHashParam` at `0x1800040d7`
- `ADVAPI32!CryptGetHashParam` at `0x1800040d7`

## pseudocode

```c
__int64 __fastcall CryptHash::GetHash(HCRYPTHASH *this, unsigned __int8 *a2, DWORD a3, unsigned int *a4)
{
  unsigned int v5; // ecx
  DWORD pdwDataLen; // [rsp+50h] [rbp+18h] BYREF

  pdwDataLen = a3;
  if ( a4 && (*a4 = 0, a2) && a3 )
  {
    if ( CryptGetHashParam(*this, 2u, a2, &pdwDataLen, 0) )
    {
      v5 = 0;
      *a4 = pdwDataLen;
    }
    else
    {
      return GetLastError();
    }
  }
  else
  {
    return 87;
  }
  return v5;
}

```

## disassembly

```asm
0x18000409c  mov     [rsp+pdwDataLen], r8d
0x1800040a1  push    rbx
0x1800040a2  sub     rsp, 30h
0x1800040a6  mov     rbx, r9
0x1800040a9  test    r9, r9
0x1800040ac  jz      short loc_1800040F5
0x1800040ae  mov     dword ptr [r9], 0
0x1800040b5  test    rdx, rdx
0x1800040b8  jz      short loc_1800040F5
0x1800040ba  test    r8d, r8d
0x1800040bd  jz      short loc_1800040F5
0x1800040bf  mov     rcx, [rcx]; hHash
0x1800040c2  lea     r9, [rsp+38h+pdwDataLen]; pdwDataLen
0x1800040c7  mov     r8, rdx; pbData
0x1800040ca  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1800040d2  mov     edx, 2; dwParam
0x1800040d7  call    cs:__imp_CryptGetHashParam
0x1800040dd  test    eax, eax
0x1800040df  jnz     short loc_1800040EB
0x1800040e1  call    cs:__imp_GetLastError
0x1800040e7  mov     ecx, eax
0x1800040e9  jmp     short loc_1800040FA
0x1800040eb  mov     eax, [rsp+38h+pdwDataLen]
0x1800040ef  xor     ecx, ecx
0x1800040f1  mov     [rbx], eax
0x1800040f3  jmp     short loc_1800040FA
0x1800040f5  mov     ecx, 57h ; 'W'
0x1800040fa  mov     eax, ecx
0x1800040fc  add     rsp, 30h
0x180004100  pop     rbx
0x180004101  retn
```
