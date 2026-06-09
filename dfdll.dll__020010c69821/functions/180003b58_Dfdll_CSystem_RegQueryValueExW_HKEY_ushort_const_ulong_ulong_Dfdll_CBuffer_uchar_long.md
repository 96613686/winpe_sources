# Dfdll::CSystem::RegQueryValueExW(HKEY__ *,ushort const *,ulong *,ulong *,Dfdll::CBuffer<uchar> &,long &)

- ea: `0x180003b58`
- end: `0x180003c3e`
- name: `?RegQueryValueExW@CSystem@Dfdll@@SAJPEAUHKEY__@@PEBGPEAK2AEAV?$CBuffer@E@2@AEAJ@Z`
- size: `230`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpValueName@<rdx>, LPDWORD lpReserved@<r8>, Dfdll::CBufferBase *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800036c8`
- `0x1800037a0`

## callees

- `0x180001fc8`
- `0x180003b58`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180003b97`
- `ADVAPI32!RegQueryValueExW` at `0x180003bfa`
- `ADVAPI32!RegQueryValueExW` at `0x180003b97`
- `ADVAPI32!RegQueryValueExW` at `0x180003bfa`

## pseudocode

```c
__int64 __fastcall Dfdll::CSystem::RegQueryValueExW(
        HKEY hKey,
        LPCWSTR lpValueName,
        LPDWORD lpReserved,
        _DWORD *a4,
        LPBYTE *a5,
        LSTATUS *a6)
{
  LSTATUS v10; // r8d
  __int64 result; // rax
  LSTATUS v12; // ecx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  DWORD Type[9]; // [rsp+34h] [rbp-24h] BYREF

  Type[0] = 0;
  cbData = 0;
  v10 = RegQueryValueExW(hKey, lpValueName, lpReserved, Type, 0, &cbData);
  *a6 = v10;
  if ( v10 )
  {
    result = (unsigned __int16)v10 | 0x80070000;
    if ( v10 <= 0 )
      return (unsigned int)v10;
  }
  else
  {
    result = Dfdll::CBufferBase::Allocate((Dfdll::CBufferBase *)a5, cbData);
    if ( (int)result >= 0 )
    {
      v12 = RegQueryValueExW(hKey, lpValueName, lpReserved, Type, a5[1], &cbData);
      *a6 = v12;
      if ( v12 )
      {
        result = (unsigned __int16)v12 | 0x80070000;
        if ( v12 <= 0 )
          return (unsigned int)v12;
      }
      else
      {
        if ( a4 )
          *a4 = Type[0];
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003b58  mov     r11, rsp
0x180003b5b  mov     [r11+8], rbx
0x180003b5f  mov     [r11+10h], rbp
0x180003b63  mov     [r11+18h], rsi
0x180003b67  push    rdi
0x180003b68  push    r14
0x180003b6a  push    r15
0x180003b6c  sub     rsp, 40h
0x180003b70  mov     rbx, r9
0x180003b73  mov     rsi, r8
0x180003b76  mov     rbp, rdx
0x180003b79  mov     r14, rcx
0x180003b7c  and     [rsp+58h+Type], 0
0x180003b81  and     [rsp+58h+cbData], 0
0x180003b86  lea     rax, [r11-28h]
0x180003b8a  mov     [r11-30h], rax
0x180003b8e  and     qword ptr [r11-38h], 0
0x180003b93  lea     r9, [r11-24h]; lpType
0x180003b97  call    cs:__imp_RegQueryValueExW
0x180003b9d  mov     r8d, eax
0x180003ba0  mov     r15, [rsp+58h+arg_28]
0x180003ba8  mov     [r15], eax
0x180003bab  test    eax, eax
0x180003bad  jz      short loc_180003BC1
0x180003baf  movzx   eax, r8w
0x180003bb3  or      eax, 80070000h
0x180003bb8  test    r8d, r8d
0x180003bbb  cmovle  eax, r8d
0x180003bbf  jmp     short loc_180003C25
0x180003bc1  mov     edx, [rsp+58h+cbData]; unsigned int
0x180003bc5  mov     rdi, [rsp+58h+arg_20]
0x180003bcd  mov     rcx, rdi; this
0x180003bd0  call    ?Allocate@CBufferBase@Dfdll@@QEAAJI@Z; Dfdll::CBufferBase::Allocate(uint)
0x180003bd5  test    eax, eax
0x180003bd7  js      short loc_180003C25
0x180003bd9  lea     rax, [rsp+58h+cbData]
0x180003bde  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180003be3  mov     rax, [rdi+8]
0x180003be7  mov     [rsp+58h+lpData], rax; lpData
0x180003bec  lea     r9, [rsp+58h+Type]; lpType
0x180003bf1  mov     r8, rsi; lpReserved
0x180003bf4  mov     rdx, rbp; lpValueName
0x180003bf7  mov     rcx, r14; hKey
0x180003bfa  call    cs:__imp_RegQueryValueExW
0x180003c00  mov     ecx, eax
0x180003c02  mov     [r15], eax
0x180003c05  test    eax, eax
0x180003c07  jz      short loc_180003C18
0x180003c09  movzx   eax, cx
0x180003c0c  or      eax, 80070000h
0x180003c11  test    ecx, ecx
0x180003c13  cmovle  eax, ecx
0x180003c16  jmp     short loc_180003C25
0x180003c18  test    rbx, rbx
0x180003c1b  jz      short loc_180003C23
0x180003c1d  mov     eax, [rsp+58h+Type]
0x180003c21  mov     [rbx], eax
0x180003c23  xor     eax, eax
0x180003c25  mov     rbx, [rsp+58h+arg_0]
0x180003c2a  mov     rbp, [rsp+58h+arg_8]
0x180003c2f  mov     rsi, [rsp+58h+arg_10]
0x180003c34  add     rsp, 40h
0x180003c38  pop     r15
0x180003c3a  pop     r14
0x180003c3c  pop     rdi
0x180003c3d  retn
```
