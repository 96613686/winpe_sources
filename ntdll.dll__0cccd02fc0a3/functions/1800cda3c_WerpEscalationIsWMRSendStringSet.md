# WerpEscalationIsWMRSendStringSet

- ea: `0x1800cda3c`
- end: `0x1800cdb11`
- name: `WerpEscalationIsWMRSendStringSet`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ccde8`

## callees

- `0x1800cda3c`
- `0x1800cdb18`
- `0x18012c830`
- `0x18015e4b0`
- `0x18015e510`

## string_xrefs

- `0x1800cda4c`: `\Registry\Machine\Software\Microsoft\SQMClient\Windows\WMR`

## pseudocode

```c
_BOOL8 WerpEscalationIsWMRSendStringSet()
{
  int v0; // ebx
  size_t v1; // rax
  int v3; // eax
  _QWORD v4[2]; // [rsp+20h] [rbp-40h] BYREF
  int v5; // [rsp+30h] [rbp-30h]
  int v6; // [rsp+34h] [rbp-2Ch]
  __int64 v7; // [rsp+38h] [rbp-28h]
  _QWORD *v8; // [rsp+40h] [rbp-20h]
  int v9; // [rsp+48h] [rbp-18h]
  _BYTE v10[20]; // [rsp+4Ch] [rbp-14h]
  int v11; // [rsp+70h] [rbp+10h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp+18h]

  v4[1] = L"\\Registry\\Machine\\Software\\Microsoft\\SQMClient\\Windows\\WMR";
  v8 = 0;
  v0 = 0;
  Handle = 0;
  *(_OWORD *)v10 = 0;
  v11 = 0;
  v6 = 0;
  v4[0] = 0;
  v1 = 2 * wcslen(L"\\Registry\\Machine\\Software\\Microsoft\\SQMClient\\Windows\\WMR");
  v5 = 48;
  v7 = 0;
  v9 = 64;
  if ( v1 >= 0xFFFE )
    LOWORD(v1) = -4;
  LOWORD(v4[0]) = v1;
  WORD1(v4[0]) = v1 + 2;
  v8 = v4;
  *(_OWORD *)&v10[4] = 0;
  if ( (int)NtOpenKey() >= 0 )
  {
    v3 = WerpEscalationReadUlongFromKey(Handle, L"WMRSendMessageString", &v11);
    v0 = v11;
    if ( v3 < 0 )
      v0 = 0;
  }
  if ( Handle )
    NtClose(Handle);
  return v0 != 0;
}

```

## disassembly

```asm
0x1800cda3c  mov     [rsp-8+arg_10], rbx
0x1800cda41  push    rbp
0x1800cda42  mov     rbp, rsp
0x1800cda45  sub     rsp, 60h
0x1800cda49  xorps   xmm0, xmm0
0x1800cda4c  lea     rcx, aRegistryMachin_3; "\\Registry\\Machine\\Software\\Microsof"...
0x1800cda53  xor     eax, eax
0x1800cda55  mov     [rbp+var_38], rcx
0x1800cda59  movups  [rbp+var_20], xmm0
0x1800cda5d  xor     ebx, ebx
0x1800cda5f  mov     [rbp+Handle], rax
0x1800cda63  movups  [rbp+var_20+0Ch], xmm0
0x1800cda67  mov     [rbp+arg_0], ebx
0x1800cda6a  movups  [rbp+var_30], xmm0
0x1800cda6e  mov     [rbp+var_40], rax
0x1800cda72  call    wcslen
0x1800cda77  add     rax, rax
0x1800cda7a  mov     dword ptr [rbp+var_30], 30h ; '0'
0x1800cda81  cmp     rax, 0FFFEh
0x1800cda87  mov     qword ptr [rbp+var_30+8], rbx
0x1800cda8b  mov     ecx, 0FFFCh
0x1800cda90  mov     dword ptr [rbp+var_20+8], 40h ; '@'
0x1800cda97  cmovnb  rax, rcx
0x1800cda9b  lea     r8, [rbp+var_30]
0x1800cda9f  mov     word ptr [rbp+var_40], ax
0x1800cdaa3  lea     rcx, [rbp+Handle]
0x1800cdaa7  add     ax, 2
0x1800cdaab  xorps   xmm0, xmm0
0x1800cdaae  mov     word ptr [rbp+var_40+2], ax
0x1800cdab2  mov     edx, 20119h
0x1800cdab7  lea     rax, [rbp+var_40]
0x1800cdabb  mov     qword ptr [rbp+var_20], rax
0x1800cdabf  movdqu  [rbp+var_10], xmm0
0x1800cdac4  call    NtOpenKey
0x1800cdac9  test    eax, eax
0x1800cdacb  jns     short loc_1800CDAF1
0x1800cdacd  mov     rcx, [rbp+Handle]; Handle
0x1800cdad1  test    rcx, rcx
0x1800cdad4  jz      short loc_1800CDADB
0x1800cdad6  call    NtClose
0x1800cdadb  xor     eax, eax
0x1800cdadd  test    ebx, ebx
0x1800cdadf  mov     rbx, [rsp+60h+arg_10]
0x1800cdae7  setnz   al
0x1800cdaea  add     rsp, 60h
0x1800cdaee  pop     rbp
0x1800cdaef  retn
0x1800cdaf1  mov     rcx, [rbp+Handle]
0x1800cdaf5  lea     r8, [rbp+arg_0]
0x1800cdaf9  lea     rdx, aWmrsendmessage; "WMRSendMessageString"
0x1800cdb00  call    WerpEscalationReadUlongFromKey
0x1800cdb05  mov     ebx, [rbp+arg_0]
0x1800cdb08  xor     ecx, ecx
0x1800cdb0a  test    eax, eax
0x1800cdb0c  cmovs   ebx, ecx
0x1800cdb0f  jmp     short loc_1800CDACD
```
