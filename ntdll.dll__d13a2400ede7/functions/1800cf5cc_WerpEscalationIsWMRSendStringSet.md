# WerpEscalationIsWMRSendStringSet

- ea: `0x1800cf5cc`
- end: `0x1800cf6a1`
- name: `WerpEscalationIsWMRSendStringSet`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ce978`

## callees

- `0x1800cf5cc`
- `0x1800cf6a8`
- `0x18012d320`
- `0x18015ecc0`
- `0x18015ed20`

## string_xrefs

- `0x1800cf5dc`: `\Registry\Machine\Software\Microsoft\SQMClient\Windows\WMR`

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
0x1800cf5cc  mov     [rsp-8+arg_10], rbx
0x1800cf5d1  push    rbp
0x1800cf5d2  mov     rbp, rsp
0x1800cf5d5  sub     rsp, 60h
0x1800cf5d9  xorps   xmm0, xmm0
0x1800cf5dc  lea     rcx, aRegistryMachin_3; "\\Registry\\Machine\\Software\\Microsof"...
0x1800cf5e3  xor     eax, eax
0x1800cf5e5  mov     [rbp+var_38], rcx
0x1800cf5e9  movups  [rbp+var_20], xmm0
0x1800cf5ed  xor     ebx, ebx
0x1800cf5ef  mov     [rbp+Handle], rax
0x1800cf5f3  movups  [rbp+var_20+0Ch], xmm0
0x1800cf5f7  mov     [rbp+arg_0], ebx
0x1800cf5fa  movups  [rbp+var_30], xmm0
0x1800cf5fe  mov     [rbp+var_40], rax
0x1800cf602  call    wcslen
0x1800cf607  add     rax, rax
0x1800cf60a  mov     dword ptr [rbp+var_30], 30h ; '0'
0x1800cf611  cmp     rax, 0FFFEh
0x1800cf617  mov     qword ptr [rbp+var_30+8], rbx
0x1800cf61b  mov     ecx, 0FFFCh
0x1800cf620  mov     dword ptr [rbp+var_20+8], 40h ; '@'
0x1800cf627  cmovnb  rax, rcx
0x1800cf62b  lea     r8, [rbp+var_30]
0x1800cf62f  mov     word ptr [rbp+var_40], ax
0x1800cf633  lea     rcx, [rbp+Handle]
0x1800cf637  add     ax, 2
0x1800cf63b  xorps   xmm0, xmm0
0x1800cf63e  mov     word ptr [rbp+var_40+2], ax
0x1800cf642  mov     edx, 20119h
0x1800cf647  lea     rax, [rbp+var_40]
0x1800cf64b  mov     qword ptr [rbp+var_20], rax
0x1800cf64f  movdqu  [rbp+var_10], xmm0
0x1800cf654  call    NtOpenKey
0x1800cf659  test    eax, eax
0x1800cf65b  jns     short loc_1800CF681
0x1800cf65d  mov     rcx, [rbp+Handle]; Handle
0x1800cf661  test    rcx, rcx
0x1800cf664  jz      short loc_1800CF66B
0x1800cf666  call    NtClose
0x1800cf66b  xor     eax, eax
0x1800cf66d  test    ebx, ebx
0x1800cf66f  mov     rbx, [rsp+60h+arg_10]
0x1800cf677  setnz   al
0x1800cf67a  add     rsp, 60h
0x1800cf67e  pop     rbp
0x1800cf67f  retn
0x1800cf681  mov     rcx, [rbp+Handle]
0x1800cf685  lea     r8, [rbp+arg_0]
0x1800cf689  lea     rdx, aWmrsendmessage; "WMRSendMessageString"
0x1800cf690  call    WerpEscalationReadUlongFromKey
0x1800cf695  mov     ebx, [rbp+arg_0]
0x1800cf698  xor     ecx, ecx
0x1800cf69a  test    eax, eax
0x1800cf69c  cmovs   ebx, ecx
0x1800cf69f  jmp     short loc_1800CF65D
```
