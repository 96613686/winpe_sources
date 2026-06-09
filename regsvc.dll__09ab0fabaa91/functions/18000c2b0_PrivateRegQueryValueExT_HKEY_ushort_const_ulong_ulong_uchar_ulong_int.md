# PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)

- ea: `0x18000c2b0`
- end: `0x18000c41d`
- name: `?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z`
- size: `365`
- prototype: `int __fastcall(HKEY KeyHandle, const unsigned __int16 *, unsigned int *, unsigned int *, unsigned __int8 *MbString, unsigned int *, int)`
- caller_count: `6`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180006a50`
- `0x180006bc0`
- `0x180008c30`
- `0x18000bc48`
- `0x18000e1a8`
- `0x1800136b0`

## callees

- `0x180005da0`
- `0x180008050`
- `0x18000bef8`
- `0x18000c2b0`
- `0x18001e431`

## import_xrefs

- `ntdll!RtlUnicodeToMultiByteN` at `0x18000c3b7`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18000c3b7`
- `ntdll!NtQueryValueKey` at `0x18000c33e`
- `ntdll!NtQueryValueKey` at `0x18000c33e`
- `ntdll!RtlInitUnicodeString` at `0x18000c2f5`
- `ntdll!RtlInitUnicodeString` at `0x18000c2f5`

## pseudocode

```c
int __fastcall PrivateRegQueryValueExT(
        HKEY KeyHandle,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned __int8 *MbString,
        unsigned int *a6,
        int a7)
{
  unsigned int *v9; // rsi
  ULONG Length; // ebx
  _DWORD *v11; // rdi
  NTSTATUS v12; // ebx
  ULONG v13; // edx
  int v14; // r8d
  ULONG v15; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-28h] BYREF
  ULONG ResultSize; // [rsp+60h] [rbp+8h] BYREF
  ULONG UnicodeSize; // [rsp+70h] [rbp+18h] BYREF
  int v20; // [rsp+74h] [rbp+1Ch]

  v20 = HIDWORD(a3);
  ResultSize = 0;
  DestinationString = 0;
  UnicodeSize = 0;
  if ( (unsigned __int64)KeyHandle - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RtlInitUnicodeString(&DestinationString, a2);
    v9 = a6;
    UnicodeSize = *a6 + 16;
    Length = UnicodeSize;
    v11 = (_DWORD *)operator new(UnicodeSize);
    if ( !v11 )
    {
      v12 = -1073741801;
      return PerfpDosError(v12);
    }
    v12 = NtQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, v11, Length, &UnicodeSize);
    if ( (int)(v12 + 0x80000000) < 0 || v12 == -2147483643 )
    {
      if ( a4 )
        *a4 = v11[1];
      v13 = v11[2];
      *v9 = v13;
      if ( v12 >= 0 )
      {
        if ( MbString )
        {
          if ( a7 || (v14 = v11[1], (unsigned int)(v14 - 1) > 1) && v14 != 7 )
          {
            if ( v11[2] > v13 )
            {
              v12 = -2147483643;
            }
            else
            {
              memcpy_0(MbString, v11 + 3, (unsigned int)v11[2]);
              v12 = 0;
            }
            v15 = v11[2];
          }
          else
          {
            ResultSize = 0;
            v12 = RtlUnicodeToMultiByteN((PCHAR)MbString, v13, &ResultSize, (PCWCH)v11 + 6, UnicodeSize);
            if ( v12 < 0 )
              goto LABEL_19;
            v15 = ResultSize;
          }
          *v9 = v15;
        }
      }
    }
LABEL_19:
    operator delete(v11);
    if ( v12 >= 0 )
      return 0;
    return PerfpDosError(v12);
  }
  return 6;
}

```

## disassembly

```asm
0x18000c2b0  mov     rax, rsp
0x18000c2b3  mov     [rax+10h], rbx
0x18000c2b7  mov     [rax+20h], rbp
0x18000c2bb  mov     [rax+18h], r8
0x18000c2bf  push    rsi
0x18000c2c0  push    rdi
0x18000c2c1  push    r14
0x18000c2c3  sub     rsp, 40h
0x18000c2c7  xorps   xmm0, xmm0
0x18000c2ca  mov     dword ptr [rax+8], 0
0x18000c2d1  movups  xmmword ptr [rax-28h], xmm0
0x18000c2d5  mov     dword ptr [rax+18h], 0
0x18000c2dc  mov     r14, r9
0x18000c2df  lea     rax, [rcx-1]
0x18000c2e3  mov     rbp, rcx
0x18000c2e6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c2ea  ja      loc_18000C405
0x18000c2f0  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x18000c2f5  call    cs:__imp_RtlInitUnicodeString
0x18000c2fb  mov     rsi, [rsp+58h+arg_28]
0x18000c303  mov     ebx, [rsi]
0x18000c305  add     ebx, 10h
0x18000c308  mov     ecx, ebx
0x18000c30a  mov     [rsp+58h+UnicodeSize], ebx
0x18000c30e  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18000c313  mov     rdi, rax
0x18000c316  test    rax, rax
0x18000c319  jz      loc_18000C3F7
0x18000c31f  lea     rax, [rsp+58h+UnicodeSize]
0x18000c324  mov     r9, rdi; KeyValueInformation
0x18000c327  mov     [rsp+58h+ResultLength], rax; ResultLength
0x18000c32c  lea     rdx, [rsp+58h+DestinationString]; ValueName
0x18000c331  mov     r8d, 2; KeyValueInformationClass
0x18000c337  mov     [rsp+58h+Length], ebx; Length
0x18000c33b  mov     rcx, rbp; KeyHandle
0x18000c33e  call    cs:__imp_NtQueryValueKey
0x18000c344  mov     ecx, 80000000h
0x18000c349  mov     r9d, 80000005h
0x18000c34f  mov     ebx, eax
0x18000c351  add     eax, ecx
0x18000c353  test    ecx, eax
0x18000c355  jnz     short loc_18000C360
0x18000c357  cmp     ebx, r9d
0x18000c35a  jnz     loc_18000C3E7
0x18000c360  test    r14, r14
0x18000c363  jz      short loc_18000C36B
0x18000c365  mov     eax, [rdi+4]
0x18000c368  mov     [r14], eax
0x18000c36b  mov     edx, [rdi+8]; MbSize
0x18000c36e  mov     [rsi], edx
0x18000c370  test    ebx, ebx
0x18000c372  js      short loc_18000C3E7
0x18000c374  mov     rcx, [rsp+58h+MbString]; void *
0x18000c37c  test    rcx, rcx
0x18000c37f  jz      short loc_18000C3E7
0x18000c381  cmp     [rsp+58h+arg_30], 0
0x18000c389  jnz     short loc_18000C3C9
0x18000c38b  mov     r8d, [rdi+4]
0x18000c38f  lea     eax, [r8-1]
0x18000c393  cmp     eax, 1
0x18000c396  jbe     short loc_18000C39E
0x18000c398  cmp     r8d, 7
0x18000c39c  jnz     short loc_18000C3C9
0x18000c39e  mov     eax, [rsp+58h+UnicodeSize]
0x18000c3a2  lea     r9, [rdi+0Ch]; UnicodeString
0x18000c3a6  lea     r8, [rsp+58h+ResultSize]; ResultSize
0x18000c3ab  mov     [rsp+58h+Length], eax; UnicodeSize
0x18000c3af  mov     [rsp+58h+ResultSize], 0
0x18000c3b7  call    cs:__imp_RtlUnicodeToMultiByteN
0x18000c3bd  mov     ebx, eax
0x18000c3bf  test    eax, eax
0x18000c3c1  js      short loc_18000C3E7
0x18000c3c3  mov     eax, [rsp+58h+ResultSize]
0x18000c3c7  jmp     short loc_18000C3E5
0x18000c3c9  cmp     [rdi+8], edx
0x18000c3cc  ja      short loc_18000C3DF
0x18000c3ce  mov     r8d, [rdi+8]; Size
0x18000c3d2  lea     rdx, [rdi+0Ch]; Src
0x18000c3d6  call    memcpy_0
0x18000c3db  xor     ebx, ebx
0x18000c3dd  jmp     short loc_18000C3E2
0x18000c3df  mov     ebx, r9d
0x18000c3e2  mov     eax, [rdi+8]
0x18000c3e5  mov     [rsi], eax
0x18000c3e7  mov     rcx, rdi; Block
0x18000c3ea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c3ef  test    ebx, ebx
0x18000c3f1  js      short loc_18000C3FC
0x18000c3f3  xor     eax, eax
0x18000c3f5  jmp     short loc_18000C40A
0x18000c3f7  mov     ebx, 0C0000017h
0x18000c3fc  mov     ecx, ebx; int
0x18000c3fe  call    ?PerfpDosError@@YAKJ@Z; PerfpDosError(long)
0x18000c403  jmp     short loc_18000C40A
0x18000c405  mov     eax, 6
0x18000c40a  mov     rbx, [rsp+58h+arg_8]
0x18000c40f  mov     rbp, [rsp+58h+arg_18]
0x18000c414  add     rsp, 40h
0x18000c418  pop     r14
0x18000c41a  pop     rdi
0x18000c41b  pop     rsi
0x18000c41c  retn
```
