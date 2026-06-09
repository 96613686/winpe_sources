# RfcommFindFirewallEntry

- ea: `0x140002e20`
- end: `0x140002ec0`
- name: `RfcommFindFirewallEntry`
- size: `160`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001800`
- `0x140003074`
- `0x140006bc0`
- `0x1400077cc`
- `0x14000b5b0`

## callees

- `0x140002e20`
- `0x140004a68`

## pseudocode

```c
__int64 __fastcall RfcommFindFirewallEntry(__int64 a1, unsigned __int64 *a2, __int64 a3)
{
  unsigned __int64 v3; // rbx
  char v4; // di

  v3 = *a2;
  v4 = 0;
  if ( (unsigned __int64 *)*a2 != a2 )
  {
    while ( (*(_DWORD *)a3 & *(_DWORD *)(v3 + 24)) != *(_DWORD *)(v3 + 24)
         || *(_DWORD *)(a3 + 4) != *(_DWORD *)(v3 + 28)
         || *(_QWORD *)(a3 + 8) != *(_QWORD *)(v3 + 32)
         || *(_BYTE *)(a3 + 16) != *(_BYTE *)(v3 + 40) )
    {
      v3 = *(_QWORD *)v3;
      v4 = 0;
      if ( (unsigned __int64 *)v3 == a2 )
        return v3 & -(__int64)(v4 != 0);
    }
    v4 = 1;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        19,
        51,
        (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
        v3);
  }
  return v3 & -(__int64)(v4 != 0);
}

```

## disassembly

```asm
0x140002e20  mov     [rsp+arg_0], rbx
0x140002e25  push    rdi
0x140002e26  sub     rsp, 30h
0x140002e2a  mov     rbx, [rdx]
0x140002e2d  xor     dil, dil
0x140002e30  cmp     rbx, rdx
0x140002e33  jz      short loc_140002EAB
0x140002e35  mov     r9d, [r8]
0x140002e38  mov     ecx, [rbx+18h]
0x140002e3b  mov     eax, ecx
0x140002e3d  and     eax, r9d
0x140002e40  cmp     eax, ecx
0x140002e42  jnz     short loc_140002E60
0x140002e44  mov     eax, [rbx+1Ch]
0x140002e47  cmp     [r8+4], eax
0x140002e4b  jnz     short loc_140002E60
0x140002e4d  mov     rax, [rbx+20h]
0x140002e51  cmp     [r8+8], rax
0x140002e55  jnz     short loc_140002E60
0x140002e57  mov     al, [rbx+28h]
0x140002e5a  cmp     [r8+10h], al
0x140002e5e  jz      short loc_140002E6D
0x140002e60  mov     rbx, [rbx]
0x140002e63  xor     dil, dil
0x140002e66  cmp     rbx, rdx
0x140002e69  jnz     short loc_140002E38
0x140002e6b  jmp     short loc_140002EAB
0x140002e6d  mov     dil, 1
0x140002e70  lea     rax, WPP_RECORDER_INITIALIZED
0x140002e77  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140002e7e  jz      short loc_140002EAB
0x140002e80  mov     rcx, cs:WPP_GLOBAL_Control
0x140002e87  lea     rax, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140002e8e  mov     r9d, 33h ; '3'
0x140002e94  mov     [rsp+38h+var_10], rbx
0x140002e99  mov     [rsp+38h+var_18], rax
0x140002e9e  mov     rcx, [rcx+40h]
0x140002ea2  lea     r8d, [r9-20h]
0x140002ea6  call    WPP_RECORDER_SF_q
0x140002eab  neg     dil
0x140002eae  sbb     rax, rax
0x140002eb1  and     rax, rbx
0x140002eb4  mov     rbx, [rsp+38h+arg_0]
0x140002eb9  add     rsp, 30h
0x140002ebd  pop     rdi
0x140002ebe  retn
```
