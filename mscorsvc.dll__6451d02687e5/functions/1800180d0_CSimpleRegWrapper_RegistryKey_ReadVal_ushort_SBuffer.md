# CSimpleRegWrapper::RegistryKey::ReadVal(ushort *,SBuffer *)

- ea: `0x1800180d0`
- end: `0x180018261`
- name: `?ReadVal@RegistryKey@CSimpleRegWrapper@@UEAA_NPEAGPEAVSBuffer@@@Z`
- size: `401`
- prototype: `bool(CSimpleRegWrapper::RegistryKey *__hidden this, unsigned __int16 *, struct SBuffer *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180001da0`
- `0x1800180d0`
- `0x18003303c`
- `0x180034fd4`
- `0x1800350c4`
- `0x18003dc30`
- `0x18003f263`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18001812e`
- `ADVAPI32!RegQueryValueExW` at `0x1800181f0`
- `ADVAPI32!RegQueryValueExW` at `0x18001812e`
- `ADVAPI32!RegQueryValueExW` at `0x1800181f0`

## string_xrefs

- `0x180018241`: `Consistency error: registry key is of wrong type`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall CSimpleRegWrapper::RegistryKey::ReadVal(HKEY *this, unsigned __int16 *a2, LPBYTE *a3)
{
  LSTATUS v6; // eax
  __int64 v7; // rdx
  size_t v8; // rsi
  DWORD v9; // esi
  unsigned int v11; // ecx
  const struct SString *v12; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v15[24]; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[528]; // [rsp+50h] [rbp-B0h] BYREF

  Type = 0;
  cbData = 522;
  v6 = RegQueryValueExW(this[2], a2, 0, &Type, Data, &cbData);
  LODWORD(v7) = v6;
  if ( v6 == 2 || v6 == 161 )
    return 0;
  if ( v6 )
  {
    if ( v6 != 234 )
      goto LABEL_18;
    v9 = cbData;
    if ( cbData > *((_DWORD *)a3 + 1) )
      SBuffer::ReallocateBuffer(a3, cbData, 1);
    *(_DWORD *)a3 = v9;
    if ( ((_BYTE)a3[1] & 0x10) != 0 )
      SBuffer::ReallocateBuffer(a3, *((unsigned int *)a3 + 1), 1);
    v7 = (unsigned int)RegQueryValueExW(this[2], a2, 0, &Type, a3[2], &cbData);
    *(_DWORD *)a3 = cbData;
    if ( (_DWORD)v7 )
    {
LABEL_18:
      v11 = (unsigned __int16)v7 | 0x80070000;
      if ( (int)v7 <= 0 )
        v11 = v7;
      ThrowHR(v11);
    }
  }
  else
  {
    v8 = cbData;
    if ( cbData > *((_DWORD *)a3 + 1) )
      SBuffer::ReallocateBuffer(a3, cbData, 1);
    *(_DWORD *)a3 = v8;
    if ( ((_BYTE)a3[1] & 0x10) != 0 )
      SBuffer::ReallocateBuffer(a3, *((unsigned int *)a3 + 1), 1);
    memcpy_0(a3[2], Data, v8);
  }
  if ( Type != 3 )
  {
    v12 = (const struct SString *)SString::SString(v15, v7, L"Consistency error: registry key is of wrong type");
    ThrowHR(-2147418113, v12);
  }
  return 1;
}

```

## disassembly

```asm
0x1800180d0  push    rbp
0x1800180d2  push    rbx
0x1800180d3  push    rsi
0x1800180d4  push    r14
0x1800180d6  push    r15
0x1800180d8  lea     rbp, [rsp-170h]
0x1800180e0  sub     rsp, 270h
0x1800180e7  mov     rax, cs:__security_cookie
0x1800180ee  xor     rax, rsp
0x1800180f1  mov     [rbp+190h+var_30], rax
0x1800180f8  mov     rbx, r8
0x1800180fb  mov     r15, rdx
0x1800180fe  mov     r14, rcx
0x180018101  and     [rsp+290h+Type], 0
0x180018106  mov     [rsp+290h+cbData], 20Ah
0x18001810e  lea     rax, [rsp+290h+cbData]
0x180018113  mov     [rsp+290h+lpcbData], rax; lpcbData
0x180018118  lea     rax, [rsp+290h+Data]
0x18001811d  mov     [rsp+290h+lpData], rax; lpData
0x180018122  lea     r9, [rsp+290h+Type]; lpType
0x180018127  xor     r8d, r8d; lpReserved
0x18001812a  mov     rcx, [rcx+10h]; hKey
0x18001812e  call    cs:__imp_RegQueryValueExW
0x180018134  mov     edx, eax
0x180018136  cmp     eax, 2
0x180018139  jz      loc_18001820D
0x18001813f  cmp     eax, 0A1h
0x180018144  jz      loc_18001820D
0x18001814a  test    eax, eax
0x18001814c  jnz     short loc_180018191
0x18001814e  mov     esi, [rsp+290h+cbData]
0x180018152  cmp     esi, [rbx+4]
0x180018155  jbe     short loc_180018165
0x180018157  lea     r8d, [rax+1]
0x18001815b  mov     edx, esi
0x18001815d  mov     rcx, rbx
0x180018160  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x180018165  mov     [rbx], esi
0x180018167  test    byte ptr [rbx+8], 10h
0x18001816b  jz      short loc_18001817E
0x18001816d  mov     r8d, 1
0x180018173  mov     edx, [rbx+4]
0x180018176  mov     rcx, rbx
0x180018179  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x18001817e  mov     r8, rsi; Size
0x180018181  lea     rdx, [rsp+290h+Data]; Src
0x180018186  mov     rcx, [rbx+10h]; void *
0x18001818a  call    memcpy_0
0x18001818f  jmp     short loc_180018202
0x180018191  cmp     eax, 0EAh
0x180018196  jnz     loc_18001822D
0x18001819c  mov     esi, [rsp+290h+cbData]
0x1800181a0  cmp     esi, [rbx+4]
0x1800181a3  jbe     short loc_1800181B5
0x1800181a5  mov     r8d, 1
0x1800181ab  mov     edx, esi
0x1800181ad  mov     rcx, rbx
0x1800181b0  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x1800181b5  mov     [rbx], esi
0x1800181b7  test    byte ptr [rbx+8], 10h
0x1800181bb  jz      short loc_1800181CE
0x1800181bd  mov     r8d, 1
0x1800181c3  mov     edx, [rbx+4]
0x1800181c6  mov     rcx, rbx
0x1800181c9  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x1800181ce  mov     rax, [rbx+10h]
0x1800181d2  lea     rcx, [rsp+290h+cbData]
0x1800181d7  mov     [rsp+290h+lpcbData], rcx; lpcbData
0x1800181dc  mov     [rsp+290h+lpData], rax; lpData
0x1800181e1  lea     r9, [rsp+290h+Type]; lpType
0x1800181e6  xor     r8d, r8d; lpReserved
0x1800181e9  mov     rdx, r15; lpValueName
0x1800181ec  mov     rcx, [r14+10h]; hKey
0x1800181f0  call    cs:__imp_RegQueryValueExW
0x1800181f6  mov     edx, eax
0x1800181f8  mov     eax, [rsp+290h+cbData]
0x1800181fc  mov     [rbx], eax
0x1800181fe  test    edx, edx
0x180018200  jnz     short loc_18001822D
0x180018202  cmp     [rsp+290h+Type], 3
0x180018207  jnz     short loc_180018241
0x180018209  mov     al, 1
0x18001820b  jmp     short loc_18001820F
0x18001820d  xor     al, al
0x18001820f  mov     rcx, [rbp+190h+var_30]
0x180018216  xor     rcx, rsp; StackCookie
0x180018219  call    __security_check_cookie
0x18001821e  add     rsp, 270h
0x180018225  pop     r15
0x180018227  pop     r14
0x180018229  pop     rsi
0x18001822a  pop     rbx
0x18001822b  pop     rbp
0x18001822c  retn
0x18001822d  movzx   ecx, dx
0x180018230  or      ecx, 80070000h
0x180018236  test    edx, edx
0x180018238  cmovle  ecx, edx; int
0x18001823b  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180018241  lea     r8, aConsistencyErr_1; "Consistency error: registry key is of w"...
0x180018248  lea     rcx, [rsp+290h+var_258]
0x18001824d  call    ??0SString@@QEAA@W4tagLiteral@0@PEBG@Z; SString::SString(SString::tagLiteral,ushort const *)
0x180018252  nop
0x180018253  mov     rdx, rax; struct SString *
0x180018256  mov     ecx, 8000FFFFh; int
0x18001825b  call    ?ThrowHR@@YAXJAEBVSString@@@Z; ThrowHR(long,SString const &)
```
