# AslRegistryGetString

- ea: `0x140827fd0`
- end: `0x14082816d`
- name: `AslRegistryGetString`
- size: `413`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1408221bc`

## callees

- `0x140403380`
- `0x1406dd6c0`
- `0x140827fd0`
- `0x1408be914`
- `0x1408bf658`
- `0x1408c14bc`
- `0x1408c2f88`

## string_xrefs

- `0x140828056`: `AslRegistryGetString`
- `0x140828093`: `AslRegistryGetString`
- `0x140828100`: `AslRegistryGetString`
- `0x140828143`: `AslRegistryGetString`

## pseudocode

```c
__int64 __fastcall AslRegistryGetString(_QWORD *a1, void *a2, const WCHAR *a3)
{
  NTSTATUS v5; // eax
  __int64 v6; // rcx
  NTSTATUS v7; // ebx
  _WORD *v8; // rax
  _WORD *v9; // rdi
  const char *v10; // r9
  int v11; // r8d
  __int64 v12; // rcx
  UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
  ULONG ResultLength; // [rsp+70h] [rbp+8h] BYREF

  *a1 = 0;
  ResultLength = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a3);
  v5 = ZwQueryValueKey(a2, &DestinationString, KeyValuePartialInformation, 0, 0, &ResultLength);
  v7 = v5;
  if ( v5 == -2147483643 || v5 == -1073741789 )
  {
    ResultLength += 2;
    v8 = (_WORD *)AslAlloc(v6, ResultLength);
    v9 = v8;
    if ( !v8 )
    {
      v7 = -1073741801;
      AslLogCallPrintf(1, (unsigned int)"AslRegistryGetString", 1348, (unsigned int)"Out of memory");
      return (unsigned int)v7;
    }
    v7 = ZwQueryValueKey(a2, &DestinationString, KeyValuePartialInformation, v8, ResultLength, &ResultLength);
    if ( v7 < 0 )
    {
      v10 = "Failed to query key value [%x]";
      v11 = 1360;
LABEL_13:
      AslLogCallPrintf(1, (unsigned int)"AslRegistryGetString", v11, (_DWORD)v10);
      goto LABEL_14;
    }
    if ( (unsigned int)(*((_DWORD *)v9 + 1) - 1) <= 1 )
    {
      v9[((unsigned __int64)*((unsigned int *)v9 + 2) >> 1) + 6] = 0;
      v7 = AslStringDuplicate(a1, v9 + 6);
      if ( v7 < 0 )
      {
        v10 = "Out of memory [%x]";
        v11 = 1378;
        goto LABEL_13;
      }
    }
    else
    {
      AslLogCallPrintf(1, (unsigned int)"AslRegistryGetString", 1368, (unsigned int)"Invalid value type");
      v7 = -1073741788;
    }
LABEL_14:
    AslFree(v12, v9);
    return (unsigned int)v7;
  }
  if ( v5 != -1073741772 )
    AslLogCallPrintf(1, (unsigned int)"AslRegistryGetString", 1334, (unsigned int)"Failed to query key value [%x]");
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140827fd0  push    rbx
0x140827fd2  push    rsi
0x140827fd3  push    rdi
0x140827fd4  push    r14
0x140827fd6  sub     rsp, 48h
0x140827fda  mov     rsi, rdx
0x140827fdd  mov     qword ptr [rcx], 0
0x140827fe4  mov     r14, rcx
0x140827fe7  mov     [rsp+68h+arg_0], 0
0x140827fef  xorps   xmm0, xmm0
0x140827ff2  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140827ff7  mov     rdx, r8; SourceString
0x140827ffa  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x140827fff  call    RtlInitUnicodeString
0x140828004  xor     r9d, r9d; KeyValueInformation
0x140828007  lea     rax, [rsp+68h+arg_0]
0x14082800c  mov     [rsp+68h+ResultLength], rax; ResultLength
0x140828011  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x140828016  mov     rcx, rsi; KeyHandle
0x140828019  mov     [rsp+68h+Length], 0; Length
0x140828021  lea     r8d, [r9+2]; KeyValueInformationClass
0x140828025  call    ZwQueryValueKey
0x14082802a  mov     ebx, eax
0x14082802c  cmp     eax, 80000005h
0x140828031  jz      short loc_14082806C
0x140828033  cmp     eax, 0C0000023h
0x140828038  jz      short loc_14082806C
0x14082803a  cmp     eax, 0C0000034h
0x14082803f  jz      loc_140828160
0x140828045  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x14082804c  mov     [rsp+68h+Length], eax
0x140828050  mov     r8d, 536h
0x140828056  lea     rdx, aAslregistryget_2; "AslRegistryGetString"
0x14082805d  mov     ecx, 1
0x140828062  call    AslLogCallPrintf
0x140828067  jmp     loc_140828160
0x14082806c  mov     eax, [rsp+68h+arg_0]
0x140828070  add     eax, 2
0x140828073  mov     edx, eax
0x140828075  mov     [rsp+68h+arg_0], eax
0x140828079  call    AslAlloc
0x14082807e  mov     rdi, rax
0x140828081  test    rax, rax
0x140828084  jnz     short loc_1408280AC
0x140828086  lea     r9, aOutOfMemory_0; "Out of memory"
0x14082808d  mov     r8d, 544h
0x140828093  lea     rdx, aAslregistryget_2; "AslRegistryGetString"
0x14082809a  mov     ebx, 0C0000017h
0x14082809f  lea     ecx, [rax+1]
0x1408280a2  call    AslLogCallPrintf
0x1408280a7  jmp     loc_140828160
0x1408280ac  lea     rax, [rsp+68h+arg_0]
0x1408280b1  mov     r9, rdi; KeyValueInformation
0x1408280b4  mov     [rsp+68h+ResultLength], rax; ResultLength
0x1408280b9  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x1408280be  mov     eax, [rsp+68h+arg_0]
0x1408280c2  mov     r8d, 2; KeyValueInformationClass
0x1408280c8  mov     rcx, rsi; KeyHandle
0x1408280cb  mov     [rsp+68h+Length], eax; Length
0x1408280cf  call    ZwQueryValueKey
0x1408280d4  mov     ebx, eax
0x1408280d6  test    eax, eax
0x1408280d8  jns     short loc_1408280E9
0x1408280da  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x1408280e1  mov     r8d, 550h
0x1408280e7  jmp     short loc_140828143
0x1408280e9  mov     eax, [rdi+4]
0x1408280ec  dec     eax
0x1408280ee  cmp     eax, 1
0x1408280f1  jbe     short loc_140828118
0x1408280f3  lea     r9, aInvalidValueTy; "Invalid value type"
0x1408280fa  mov     r8d, 558h
0x140828100  lea     rdx, aAslregistryget_2; "AslRegistryGetString"
0x140828107  mov     ecx, 1
0x14082810c  call    AslLogCallPrintf
0x140828111  mov     ebx, 0C0000024h
0x140828116  jmp     short loc_140828158
0x140828118  mov     ecx, [rdi+8]
0x14082811b  lea     rdx, [rdi+0Ch]
0x14082811f  shr     rcx, 1
0x140828122  xor     eax, eax
0x140828124  mov     [rdx+rcx*2], ax
0x140828128  mov     rcx, r14
0x14082812b  call    AslStringDuplicate
0x140828130  mov     ebx, eax
0x140828132  test    eax, eax
0x140828134  jns     short loc_140828158
0x140828136  lea     r9, aOutOfMemoryX; "Out of memory [%x]"
0x14082813d  mov     r8d, 562h
0x140828143  lea     rdx, aAslregistryget_2; "AslRegistryGetString"
0x14082814a  mov     [rsp+68h+Length], eax
0x14082814e  mov     ecx, 1
0x140828153  call    AslLogCallPrintf
0x140828158  mov     rdx, rdi
0x14082815b  call    AslFree
0x140828160  mov     eax, ebx
0x140828162  add     rsp, 48h
0x140828166  pop     r14
0x140828168  pop     rdi
0x140828169  pop     rsi
0x14082816a  pop     rbx
0x14082816b  retn
```
