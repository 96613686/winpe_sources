# RfcommValidateFirewallRequest

- ea: `0x140032cf8`
- end: `0x140032d98`
- name: `RfcommValidateFirewallRequest`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002ac8`

## callees

- `0x140004684`
- `0x140032cf8`

## pseudocode

```c
__int64 __fastcall RfcommValidateFirewallRequest(int *a1)
{
  int v1; // r8d
  char v2; // al
  unsigned int v3; // ebx

  v1 = *a1;
  if ( ((*a1 - 1) & 0xFFFFFFFC) != 0 || v1 == 3 )
  {
    v3 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Dd(
        WPP_GLOBAL_Control->DeviceExtension,
        (unsigned int)&WPP_RECORDER_INITIALIZED,
        19,
        49,
        (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
        v1,
        13);
  }
  else
  {
    v2 = *((_BYTE *)a1 + 16);
    if ( !v2 || (v3 = 0, (unsigned __int8)v2 > 0x1Eu) )
    {
      v3 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_Dd(
          WPP_GLOBAL_Control->DeviceExtension,
          (unsigned int)&WPP_RECORDER_INITIALIZED,
          19,
          50,
          (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
          v2,
          13);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x140032cf8  push    rbx
0x140032cfa  sub     rsp, 40h
0x140032cfe  mov     r8d, [rcx]
0x140032d01  lea     eax, [r8-1]
0x140032d05  test    eax, 0FFFFFFFCh
0x140032d0a  jnz     short loc_140032D47
0x140032d0c  cmp     r8d, 3
0x140032d10  jz      short loc_140032D47
0x140032d12  movzx   eax, byte ptr [rcx+10h]
0x140032d16  cmp     al, 1
0x140032d18  jb      short loc_140032D20
0x140032d1a  xor     ebx, ebx
0x140032d1c  cmp     al, 1Eh
0x140032d1e  jbe     short loc_140032D8F
0x140032d20  mov     ecx, 0C000000Dh
0x140032d25  mov     ebx, ecx
0x140032d27  lea     rdx, WPP_RECORDER_INITIALIZED
0x140032d2e  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140032d35  jz      short loc_140032D8F
0x140032d37  mov     [rsp+48h+var_18], ecx
0x140032d3b  mov     r9d, 32h ; '2'
0x140032d41  mov     [rsp+48h+var_20], eax
0x140032d45  jmp     short loc_140032D6D
0x140032d47  mov     ecx, 0C000000Dh
0x140032d4c  mov     ebx, ecx
0x140032d4e  lea     rdx, WPP_RECORDER_INITIALIZED
0x140032d55  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140032d5c  jz      short loc_140032D8F
0x140032d5e  mov     [rsp+48h+var_18], ecx
0x140032d62  mov     r9d, 31h ; '1'
0x140032d68  mov     [rsp+48h+var_20], r8d
0x140032d6d  mov     rcx, cs:WPP_GLOBAL_Control
0x140032d74  lea     rax, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140032d7b  mov     r8d, 13h
0x140032d81  mov     [rsp+48h+var_28], rax
0x140032d86  mov     rcx, [rcx+40h]
0x140032d8a  call    WPP_RECORDER_SF_Dd
0x140032d8f  mov     eax, ebx
0x140032d91  add     rsp, 40h
0x140032d95  pop     rbx
0x140032d96  retn
```
