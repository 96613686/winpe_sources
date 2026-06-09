# GetAccountRootKeyByInitiationId

- ea: `0x18000c974`
- end: `0x18000ca58`
- name: `GetAccountRootKeyByInitiationId`
- size: `228`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ef50`
- `0x18000fc34`
- `0x180014a60`
- `0x180018480`
- `0x18001b0d0`

## callees

- `0x18000c920`
- `0x18000c974`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000c9d4`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000c9d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ca36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ca36`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000c994`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000c994`
- `DMCmnUtils!CopyString` at `0x18000ca09`
- `DMCmnUtils!CopyString` at `0x18000ca09`

## pseudocode

```c
__int64 __fastcall GetAccountRootKeyByInitiationId(__int64 a1, __int64 a2)
{
  char IsStateSeparationEnabled; // al
  const wchar_t *v5; // r8
  __int64 v6; // rax
  __int64 v7; // rdi
  wchar_t *v8; // rax
  int AccountRootKey; // ebx
  unsigned __int64 v10; // rax
  __int64 v11; // rdx
  HLOCAL hMem; // [rsp+40h] [rbp+8h] BYREF

  hMem = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1);
  v5 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
  if ( !IsStateSeparationEnabled )
    v5 = L"Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
  v6 = -1;
  do
    ++v6;
  while ( v5[v6] );
  v7 = 2LL * (unsigned int)(v6 + 1);
  v8 = wcschr((const wchar_t *)(v7 + a1), 0x5Cu);
  if ( v8 )
  {
    v10 = ((__int64)&v8[v7 / 0xFFFFFFFFFFFFFFFEuLL] - a1) >> 1;
    if ( v10 > 0xFFFFFFFF )
    {
      AccountRootKey = -2147024362;
    }
    else
    {
      AccountRootKey = CopyString((const unsigned __int16 *)(v7 + a1), v10, (unsigned __int16 **)&hMem);
      if ( AccountRootKey >= 0 )
        AccountRootKey = GetAccountRootKey(hMem, v11, a2);
    }
  }
  else
  {
    AccountRootKey = -2147024809;
  }
  LocalFree(hMem);
  return (unsigned int)AccountRootKey;
}

```

## disassembly

```asm
0x18000c974  mov     [rsp+arg_8], rbx
0x18000c979  mov     [rsp+arg_10], rbp
0x18000c97e  push    rsi
0x18000c97f  push    rdi
0x18000c980  push    r14
0x18000c982  sub     rsp, 20h
0x18000c986  xor     r14d, r14d
0x18000c989  mov     rbp, rdx
0x18000c98c  mov     [rsp+38h+hMem], r14
0x18000c991  mov     rbx, rcx
0x18000c994  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000c99b  nop     dword ptr [rax+rax+00h]
0x18000c9a0  test    al, al
0x18000c9a2  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Provisioning\\OMAD"...
0x18000c9a9  lea     r8, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x18000c9b0  cmovz   r8, rcx
0x18000c9b4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c9b8  inc     rax
0x18000c9bb  cmp     [r8+rax*2], r14w
0x18000c9c0  jnz     short loc_18000C9B8
0x18000c9c2  inc     eax
0x18000c9c4  mov     edx, 5Ch ; '\'; Ch
0x18000c9c9  lea     rdi, [rax+rax]
0x18000c9cd  lea     rsi, [rdi+rbx]
0x18000c9d1  mov     rcx, rsi; Str
0x18000c9d4  call    cs:__imp_wcschr
0x18000c9db  nop     dword ptr [rax+rax+00h]
0x18000c9e0  test    rax, rax
0x18000c9e3  jnz     short loc_18000C9EC
0x18000c9e5  mov     ebx, 80070057h
0x18000c9ea  jmp     short loc_18000CA31
0x18000c9ec  sub     rax, rdi
0x18000c9ef  mov     ecx, 0FFFFFFFFh
0x18000c9f4  sub     rax, rbx
0x18000c9f7  sar     rax, 1
0x18000c9fa  cmp     rax, rcx
0x18000c9fd  ja      short loc_18000CA2C
0x18000c9ff  mov     edx, eax
0x18000ca01  lea     r8, [rsp+38h+hMem]
0x18000ca06  mov     rcx, rsi
0x18000ca09  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18000ca10  nop     dword ptr [rax+rax+00h]
0x18000ca15  mov     ebx, eax
0x18000ca17  test    eax, eax
0x18000ca19  js      short loc_18000CA31
0x18000ca1b  mov     rcx, [rsp+38h+hMem]
0x18000ca20  mov     r8, rbp
0x18000ca23  call    GetAccountRootKey
0x18000ca28  mov     ebx, eax
0x18000ca2a  jmp     short loc_18000CA31
0x18000ca2c  mov     ebx, 80070216h
0x18000ca31  mov     rcx, [rsp+38h+hMem]; hMem
0x18000ca36  call    cs:__imp_LocalFree
0x18000ca3d  nop     dword ptr [rax+rax+00h]
0x18000ca42  mov     rbp, [rsp+38h+arg_10]
0x18000ca47  mov     eax, ebx
0x18000ca49  mov     rbx, [rsp+38h+arg_8]
0x18000ca4e  add     rsp, 20h
0x18000ca52  pop     r14
0x18000ca54  pop     rdi
0x18000ca55  pop     rsi
0x18000ca56  retn
```
