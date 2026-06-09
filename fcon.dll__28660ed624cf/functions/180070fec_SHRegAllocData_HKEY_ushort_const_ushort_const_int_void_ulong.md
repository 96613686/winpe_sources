# SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)

- ea: `0x180070fec`
- end: `0x18007113d`
- name: `?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z`
- size: `337`
- prototype: `__int64 __usercall@<rax>(HKEY hkey@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, int@<r9d>, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180070f98`

## callees

- `0x180003220`
- `0x180004bff`
- `0x180070fec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180071054`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800710c6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180071054`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800710c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007106f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007106f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800710e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800710e7`

## pseudocode

```c
__int64 __fastcall SHRegAllocData(
        HKEY hkey,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        void **a5,
        unsigned int *a6)
{
  LSTATUS ValueW; // eax
  int v9; // ebx
  void *pvData; // rax
  DWORD pcbData[4]; // [rsp+40h] [rbp-138h] BYREF
  _BYTE Src[256]; // [rsp+50h] [rbp-128h] BYREF

  pcbData[0] = 256;
  ValueW = RegGetValueW(hkey, 0, a3, 8u, 0, Src, pcbData);
  v9 = ValueW;
  if ( !ValueW || ValueW == 234 )
  {
    pvData = CoTaskMemAlloc(pcbData[0]);
    *a5 = pvData;
    if ( pvData )
    {
      if ( !v9 )
      {
        memcpy_0(pvData, Src, pcbData[0]);
        if ( a6 )
          *a6 = pcbData[0];
        return (unsigned int)v9;
      }
      if ( !RegGetValueW(hkey, 0, a3, 8u, 0, pvData, pcbData) )
      {
        if ( a6 )
          *a6 = pcbData[0];
        return 0;
      }
      v9 = 1003;
      CoTaskMemFree(*a5);
    }
    else
    {
      v9 = 14;
    }
  }
  *a5 = 0;
  if ( a6 )
    *a6 = 0;
  if ( v9 > 0 )
    return (unsigned __int16)v9 | 0x80070000;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180070fec  mov     [rsp+arg_8], rbx
0x180070ff1  mov     [rsp+arg_18], rbp
0x180070ff6  push    rsi
0x180070ff7  push    rdi
0x180070ff8  push    r14
0x180070ffa  sub     rsp, 160h
0x180071001  mov     rax, cs:__security_cookie
0x180071008  xor     rax, rsp
0x18007100b  mov     [rsp+178h+var_28], rax
0x180071013  mov     rsi, [rsp+178h+arg_20]
0x18007101b  lea     rax, [rsp+178h+var_138]
0x180071020  mov     rdi, [rsp+178h+arg_28]
0x180071028  xor     edx, edx; lpSubKey
0x18007102a  mov     [rsp+178h+pcbData], rax; pcbData
0x18007102f  mov     r14, r8
0x180071032  lea     rax, [rsp+178h+Src]
0x180071037  mov     [rsp+178h+var_138], 100h
0x18007103f  mov     [rsp+178h+pvData], rax; pvData
0x180071044  mov     rbp, rcx
0x180071047  lea     r9d, [rdx+8]; dwFlags
0x18007104b  mov     [rsp+178h+pdwType], 0; pdwType
0x180071054  call    cs:__imp_RegGetValueW
0x18007105a  mov     ebx, eax
0x18007105c  test    eax, eax
0x18007105e  jz      short loc_18007106B
0x180071060  cmp     eax, 0EAh
0x180071065  jnz     loc_1800710F4
0x18007106b  mov     ecx, [rsp+178h+var_138]; cb
0x18007106f  call    cs:__imp_CoTaskMemAlloc
0x180071075  mov     [rsi], rax
0x180071078  test    rax, rax
0x18007107b  jz      short loc_1800710EF
0x18007107d  test    ebx, ebx
0x18007107f  jnz     short loc_1800710A0
0x180071081  mov     r8d, [rsp+178h+var_138]; Size
0x180071086  lea     rdx, [rsp+178h+Src]; Src
0x18007108b  mov     rcx, rax; void *
0x18007108e  call    memcpy_0
0x180071093  test    rdi, rdi
0x180071096  jz      short loc_180071113
0x180071098  mov     eax, [rsp+178h+var_138]
0x18007109c  mov     [rdi], eax
0x18007109e  jmp     short loc_180071113
0x1800710a0  lea     rcx, [rsp+178h+var_138]
0x1800710a5  mov     r9d, 8; dwFlags
0x1800710ab  mov     [rsp+178h+pcbData], rcx; pcbData
0x1800710b0  mov     r8, r14; lpValue
0x1800710b3  mov     [rsp+178h+pvData], rax; pvData
0x1800710b8  mov     rcx, rbp; hkey
0x1800710bb  xor     edx, edx; lpSubKey
0x1800710bd  mov     [rsp+178h+pdwType], 0; pdwType
0x1800710c6  call    cs:__imp_RegGetValueW
0x1800710cc  test    eax, eax
0x1800710ce  jnz     short loc_1800710DF
0x1800710d0  test    rdi, rdi
0x1800710d3  jz      short loc_1800710DB
0x1800710d5  mov     eax, [rsp+178h+var_138]
0x1800710d9  mov     [rdi], eax
0x1800710db  xor     ebx, ebx
0x1800710dd  jmp     short loc_180071113
0x1800710df  mov     rcx, [rsi]; pv
0x1800710e2  mov     ebx, 3EBh
0x1800710e7  call    cs:__imp_CoTaskMemFree
0x1800710ed  jmp     short loc_1800710F4
0x1800710ef  mov     ebx, 0Eh
0x1800710f4  mov     qword ptr [rsi], 0
0x1800710fb  test    rdi, rdi
0x1800710fe  jz      short loc_180071106
0x180071100  mov     dword ptr [rdi], 0
0x180071106  test    ebx, ebx
0x180071108  jle     short loc_180071113
0x18007110a  movzx   ebx, bx
0x18007110d  or      ebx, 80070000h
0x180071113  mov     eax, ebx
0x180071115  mov     rcx, [rsp+178h+var_28]
0x18007111d  xor     rcx, rsp; StackCookie
0x180071120  call    __security_check_cookie
0x180071125  lea     r11, [rsp+178h+var_18]
0x18007112d  mov     rbx, [r11+28h]
0x180071131  mov     rbp, [r11+38h]
0x180071135  mov     rsp, r11
0x180071138  pop     r14
0x18007113a  pop     rdi
0x18007113b  pop     rsi
0x18007113c  retn
```
