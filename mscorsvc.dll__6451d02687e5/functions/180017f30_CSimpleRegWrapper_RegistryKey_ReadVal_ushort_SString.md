# CSimpleRegWrapper::RegistryKey::ReadVal(ushort *,SString *)

- ea: `0x180017f30`
- end: `0x1800180c6`
- name: `?ReadVal@RegistryKey@CSimpleRegWrapper@@UEAA_NPEAGPEAVSString@@@Z`
- size: `406`
- prototype: `bool(CSimpleRegWrapper::RegistryKey *__hidden this, unsigned __int16 *, struct SString *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180001da0`
- `0x180017f30`
- `0x180030ab8`
- `0x180032f44`
- `0x18003303c`
- `0x180034fd4`
- `0x1800350c4`
- `0x18003dc30`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180017f89`
- `ADVAPI32!RegQueryValueExW` at `0x180018046`
- `ADVAPI32!RegQueryValueExW` at `0x180017f89`
- `ADVAPI32!RegQueryValueExW` at `0x180018046`

## string_xrefs

- `0x1800180a6`: `Consistency error: registry key is of wrong type`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall CSimpleRegWrapper::RegistryKey::ReadVal(HKEY *this, unsigned __int16 *a2, LPBYTE *a3)
{
  LSTATUS v6; // eax
  __int64 v7; // rdx
  DWORD v8; // edi
  int v9; // edx
  unsigned int v10; // edi
  BYTE *v11; // rcx
  unsigned int v13; // ecx
  const struct SString *v14; // rax
  DWORD cbData; // [rsp+30h] [rbp-268h] BYREF
  DWORD Type; // [rsp+34h] [rbp-264h] BYREF
  _BYTE v17[24]; // [rsp+38h] [rbp-260h] BYREF
  unsigned __int16 Data[264]; // [rsp+50h] [rbp-248h] BYREF

  Type = 0;
  cbData = 522;
  v6 = RegQueryValueExW(this[2], a2, 0, &Type, (LPBYTE)Data, &cbData);
  if ( v6 == 2 || v6 == 161 )
    return 0;
  if ( v6 )
  {
    if ( v6 != 234 )
      goto LABEL_20;
    if ( cbData )
      v8 = (cbData - 1) >> 1;
    else
      v8 = 0;
    SString::Resize(a3, v8, 4);
    v9 = *((_DWORD *)a3 + 2);
    v10 = (v8 + 1) << ((v9 & 1) == 0);
    if ( v10 > *((_DWORD *)a3 + 1) )
    {
      SBuffer::ReallocateBuffer(a3, v10, 1);
      v9 = *((_DWORD *)a3 + 2);
    }
    *(_DWORD *)a3 = v10;
    if ( (v9 & 0x10) != 0 )
      SBuffer::ReallocateBuffer(a3, *((unsigned int *)a3 + 1), 1);
    v6 = RegQueryValueExW(this[2], a2, 0, &Type, a3[2], &cbData);
    v11 = &a3[2][*(unsigned int *)a3];
    if ( ((_BYTE)a3[1] & 1) != 0 )
      *(v11 - 1) = 0;
    else
      *((_WORD *)v11 - 1) = 0;
    if ( v6 )
    {
LABEL_20:
      v13 = (unsigned __int16)v6 | 0x80070000;
      if ( v6 <= 0 )
        v13 = v6;
      ThrowHR(v13);
    }
  }
  else
  {
    SString::Set((SString *)a3, Data);
  }
  if ( Type != 1 )
  {
    v14 = (const struct SString *)SString::SString(v17, v7, L"Consistency error: registry key is of wrong type");
    ThrowHR(-2147418113, v14);
  }
  return 1;
}

```

## disassembly

```asm
0x180017f30  push    rbx
0x180017f32  push    rbp
0x180017f33  push    rsi
0x180017f34  push    rdi
0x180017f35  push    r14
0x180017f37  sub     rsp, 270h
0x180017f3e  mov     rax, cs:__security_cookie
0x180017f45  xor     rax, rsp
0x180017f48  mov     [rsp+298h+var_38], rax
0x180017f50  mov     rbx, r8
0x180017f53  mov     rbp, rdx
0x180017f56  mov     rsi, rcx
0x180017f59  xor     r14d, r14d
0x180017f5c  mov     [rsp+298h+Type], r14d
0x180017f61  mov     [rsp+298h+cbData], 20Ah
0x180017f69  lea     rax, [rsp+298h+cbData]
0x180017f6e  mov     [rsp+298h+lpcbData], rax; lpcbData
0x180017f73  lea     rax, [rsp+298h+Data]
0x180017f78  mov     [rsp+298h+lpData], rax; lpData
0x180017f7d  lea     r9, [rsp+298h+Type]; lpType
0x180017f82  xor     r8d, r8d; lpReserved
0x180017f85  mov     rcx, [rcx+10h]; hKey
0x180017f89  call    cs:__imp_RegQueryValueExW
0x180017f8f  cmp     eax, 2
0x180017f92  jz      loc_180018072
0x180017f98  cmp     eax, 0A1h
0x180017f9d  jz      loc_180018072
0x180017fa3  test    eax, eax
0x180017fa5  jnz     short loc_180017FB9
0x180017fa7  lea     rdx, [rsp+298h+Data]; unsigned __int16 *
0x180017fac  mov     rcx, rbx; this
0x180017faf  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x180017fb4  jmp     loc_180018067
0x180017fb9  cmp     eax, 0EAh
0x180017fbe  jnz     loc_180018092
0x180017fc4  mov     edi, [rsp+298h+cbData]
0x180017fc8  test    edi, edi
0x180017fca  jnz     short loc_180017FD1
0x180017fcc  mov     edi, r14d
0x180017fcf  jmp     short loc_180017FD5
0x180017fd1  dec     edi
0x180017fd3  shr     edi, 1
0x180017fd5  xor     r9d, r9d
0x180017fd8  lea     r8d, [r9+4]
0x180017fdc  mov     edx, edi
0x180017fde  mov     rcx, rbx
0x180017fe1  call    ?Resize@SString@@AEAAXIW4Representation@1@W4Preserve@SBuffer@@@Z; SString::Resize(uint,SString::Representation,SBuffer::Preserve)
0x180017fe6  mov     edx, [rbx+8]
0x180017fe9  mov     ecx, edx
0x180017feb  not     ecx
0x180017fed  and     ecx, 1
0x180017ff0  inc     edi
0x180017ff2  shl     edi, cl
0x180017ff4  cmp     edi, [rbx+4]
0x180017ff7  jbe     short loc_18001800C
0x180017ff9  mov     r8d, 1
0x180017fff  mov     edx, edi
0x180018001  mov     rcx, rbx
0x180018004  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x180018009  mov     edx, [rbx+8]
0x18001800c  mov     [rbx], edi
0x18001800e  test    dl, 10h
0x180018011  jz      short loc_180018024
0x180018013  mov     r8d, 1
0x180018019  mov     edx, [rbx+4]
0x18001801c  mov     rcx, rbx
0x18001801f  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x180018024  mov     rax, [rbx+10h]
0x180018028  lea     rcx, [rsp+298h+cbData]
0x18001802d  mov     [rsp+298h+lpcbData], rcx; lpcbData
0x180018032  mov     [rsp+298h+lpData], rax; lpData
0x180018037  lea     r9, [rsp+298h+Type]; lpType
0x18001803c  xor     r8d, r8d; lpReserved
0x18001803f  mov     rdx, rbp; lpValueName
0x180018042  mov     rcx, [rsi+10h]; hKey
0x180018046  call    cs:__imp_RegQueryValueExW
0x18001804c  mov     ecx, [rbx]
0x18001804e  add     rcx, [rbx+10h]
0x180018052  test    byte ptr [rbx+8], 1
0x180018056  jz      short loc_18001805E
0x180018058  mov     [rcx-1], r14b
0x18001805c  jmp     short loc_180018063
0x18001805e  mov     [rcx-2], r14w
0x180018063  test    eax, eax
0x180018065  jnz     short loc_180018092
0x180018067  cmp     [rsp+298h+Type], 1
0x18001806c  jnz     short loc_1800180A6
0x18001806e  mov     al, 1
0x180018070  jmp     short loc_180018074
0x180018072  xor     al, al
0x180018074  mov     rcx, [rsp+298h+var_38]
0x18001807c  xor     rcx, rsp; StackCookie
0x18001807f  call    __security_check_cookie
0x180018084  add     rsp, 270h
0x18001808b  pop     r14
0x18001808d  pop     rdi
0x18001808e  pop     rsi
0x18001808f  pop     rbp
0x180018090  pop     rbx
0x180018091  retn
0x180018092  movzx   ecx, ax
0x180018095  or      ecx, 80070000h
0x18001809b  test    eax, eax
0x18001809d  cmovle  ecx, eax; int
0x1800180a0  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800180a6  lea     r8, aConsistencyErr_1; "Consistency error: registry key is of w"...
0x1800180ad  lea     rcx, [rsp+298h+var_260]
0x1800180b2  call    ??0SString@@QEAA@W4tagLiteral@0@PEBG@Z; SString::SString(SString::tagLiteral,ushort const *)
0x1800180b7  nop
0x1800180b8  mov     rdx, rax; struct SString *
0x1800180bb  mov     ecx, 8000FFFFh; int
0x1800180c0  call    ?ThrowHR@@YAXJAEBVSString@@@Z; ThrowHR(long,SString const &)
```
