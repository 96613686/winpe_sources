# NfsSetNetworkNameOnInstance

- ea: `0x180019818`
- end: `0x180019937`
- name: `NfsSetNetworkNameOnInstance`
- size: `287`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a9b4`
- `0x18001ab54`
- `0x18001ae1c`
- `0x18001b0bc`

## callees

- `0x180018b28`
- `0x180019818`
- `0x180021dfc`
- `0x180035b40`

## import_xrefs

- `ntdll!RtlStringFromGUID` at `0x1800198ba`
- `ntdll!RtlStringFromGUID` at `0x1800198ba`
- `ntdll!RtlFreeUnicodeString` at `0x180019901`
- `ntdll!RtlFreeUnicodeString` at `0x180019901`
- `KERNEL32!GetLastError` at `0x18001987f`
- `KERNEL32!GetLastError` at `0x18001987f`
- `KERNEL32!LocalFree` at `0x1800198f7`
- `KERNEL32!LocalFree` at `0x1800198f7`
- `KERNEL32!GetComputerNameExW` at `0x180019875`
- `KERNEL32!GetComputerNameExW` at `0x180019875`

## pseudocode

```c
__int64 __fastcall NfsSetNetworkNameOnInstance(MI_Instance *self, char a2, GUID *a3)
{
  MI_Result v3; // edi
  MI_Type v5; // r9d
  int LastError; // esi
  MI_Type v7; // r9d
  void *v8; // rbx
  MI_Uint32 v10; // [rsp+20h] [rbp-39h]
  DWORD nSize[2]; // [rsp+30h] [rbp-29h] BYREF
  MI_Value value; // [rsp+38h] [rbp-21h] BYREF
  GUID Guid; // [rsp+60h] [rbp+7h] BYREF
  struct _UNICODE_STRING Buffer; // [rsp+70h] [rbp+17h] BYREF

  v3 = MI_RESULT_OK;
  Guid = *a3;
  memset(&value, 0, sizeof(value));
  if ( a2 )
  {
    nSize[0] = 16;
    if ( GetComputerNameExW(ComputerNamePhysicalNetBIOS, &Buffer.Length, nSize) )
    {
      LastError = 0;
      value.uint64 = (MI_Uint64)&Buffer;
      v3 = MI_Instance_SetElement_0(self, L"NetworkName", &value, v5, v10);
    }
    else
    {
      LastError = GetLastError();
    }
  }
  else
  {
    *(_QWORD *)nSize = 0;
    Buffer = 0;
    if ( RtlStringFromGUID(&Guid, &Buffer) < 0 )
      return (unsigned int)v3;
    LastError = NfsGetResourceNameForResourceGuid(Buffer.Buffer, (unsigned __int16 **)nSize);
    if ( !LastError )
    {
      v8 = *(void **)nSize;
      value.uint64 = *(_QWORD *)nSize;
      v3 = MI_Instance_SetElement_0(self, L"NetworkName", &value, v7, v10);
      LocalFree(v8);
    }
    RtlFreeUnicodeString(&Buffer);
  }
  if ( LastError )
    return 1;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180019818  mov     [rsp-8+arg_8], rbx
0x18001981d  mov     [rsp-8+arg_18], rsi
0x180019822  push    rbp
0x180019823  push    rdi
0x180019824  push    r14
0x180019826  lea     rbp, [rsp-47h]
0x18001982b  sub     rsp, 0A0h
0x180019832  mov     rax, cs:__security_cookie
0x180019839  xor     rax, rsp
0x18001983c  mov     [rbp+57h+var_20], rax
0x180019840  movups  xmm0, xmmword ptr [r8]
0x180019844  xor     eax, eax
0x180019846  xor     edi, edi
0x180019848  mov     qword ptr [rbp+57h+value+20h], rax
0x18001984c  mov     r14, rcx
0x18001984f  movdqu  xmmword ptr [rbp+57h+Guid.Data1], xmm0
0x180019854  xorps   xmm0, xmm0
0x180019857  movups  xmmword ptr [rbp+57h+value], xmm0
0x18001985b  movups  xmmword ptr [rbp+57h+value+10h], xmm0
0x18001985f  test    dl, dl
0x180019861  jz      short loc_1800198AA
0x180019863  lea     r8, [rbp+57h+nSize]; nSize
0x180019867  mov     [rbp+57h+nSize], 10h
0x18001986e  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x180019872  lea     ecx, [rdi+4]; NameType
0x180019875  call    cs:__imp_GetComputerNameExW
0x18001987b  test    eax, eax
0x18001987d  jnz     short loc_180019889
0x18001987f  call    cs:__imp_GetLastError
0x180019885  mov     esi, eax
0x180019887  jmp     short loc_180019907
0x180019889  lea     rax, [rbp+57h+Buffer]
0x18001988d  xor     esi, esi
0x18001988f  lea     r8, [rbp+57h+value]; value
0x180019893  mov     qword ptr [rbp+57h+value], rax
0x180019897  lea     rdx, name; "NetworkName"
0x18001989e  mov     rcx, r14; self
0x1800198a1  call    MI_Instance_SetElement_0
0x1800198a6  mov     edi, eax
0x1800198a8  jmp     short loc_180019907
0x1800198aa  lea     rdx, [rbp+57h+Buffer]; GuidString
0x1800198ae  mov     qword ptr [rbp+57h+nSize], rax
0x1800198b2  lea     rcx, [rbp+57h+Guid]; Guid
0x1800198b6  movups  xmmword ptr [rbp+57h+Buffer.Length], xmm0
0x1800198ba  call    cs:__imp_RtlStringFromGUID
0x1800198c0  test    eax, eax
0x1800198c2  js      short loc_180019911
0x1800198c4  mov     rcx, [rbp+57h+Buffer.Buffer]; unsigned __int16 *
0x1800198c8  lea     rdx, [rbp+57h+nSize]; unsigned __int16 **
0x1800198cc  call    ?NfsGetResourceNameForResourceGuid@@YAKPEAGPEAPEAG@Z; NfsGetResourceNameForResourceGuid(ushort *,ushort * *)
0x1800198d1  mov     esi, eax
0x1800198d3  test    eax, eax
0x1800198d5  jnz     short loc_1800198FD
0x1800198d7  mov     rbx, qword ptr [rbp+57h+nSize]
0x1800198db  lea     r8, [rbp+57h+value]; value
0x1800198df  lea     rdx, name; "NetworkName"
0x1800198e6  mov     qword ptr [rbp+57h+value], rbx
0x1800198ea  mov     rcx, r14; self
0x1800198ed  call    MI_Instance_SetElement_0
0x1800198f2  mov     rcx, rbx; hMem
0x1800198f5  mov     edi, eax
0x1800198f7  call    cs:__imp_LocalFree
0x1800198fd  lea     rcx, [rbp+57h+Buffer]; UnicodeString
0x180019901  call    cs:__imp_RtlFreeUnicodeString
0x180019907  test    esi, esi
0x180019909  mov     eax, 1
0x18001990e  cmovnz  edi, eax
0x180019911  mov     eax, edi
0x180019913  mov     rcx, [rbp+57h+var_20]
0x180019917  xor     rcx, rsp; StackCookie
0x18001991a  call    __security_check_cookie
0x18001991f  lea     r11, [rsp+0B0h+var_10]
0x180019927  mov     rbx, [r11+28h]
0x18001992b  mov     rsi, [r11+38h]
0x18001992f  mov     rsp, r11
0x180019932  pop     r14
0x180019934  pop     rdi
0x180019935  pop     rbp
0x180019936  retn
```
