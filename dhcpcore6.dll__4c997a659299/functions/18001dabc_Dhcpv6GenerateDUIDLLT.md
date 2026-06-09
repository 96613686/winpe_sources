# Dhcpv6GenerateDUIDLLT

- ea: `0x18001dabc`
- end: `0x18001dc7e`
- name: `Dhcpv6GenerateDUIDLLT`
- size: `450`
- prototype: `__int64 __fastcall(unsigned int *, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001d9d8`

## callees

- `0x180007564`
- `0x18000c740`
- `0x18001a3ee`
- `0x18001d640`
- `0x18001dabc`
- `0x18003098c`
- `0x1800338c0`
- `0x180033900`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18001dbf0`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18001dbf0`
- `WS2_32!__imp_htonl` at `0x18001dc02`
- `WS2_32!__imp_htonl` at `0x18001dc02`
- `WS2_32!__imp_htons` at `0x18001dbb5`
- `WS2_32!__imp_htons` at `0x18001dbd3`
- `WS2_32!__imp_htons` at `0x18001dbb5`
- `WS2_32!__imp_htons` at `0x18001dbd3`

## pseudocode

```c
__int64 __fastcall Dhcpv6GenerateDUIDLLT(unsigned int *a1, __int64 *a2)
{
  unsigned int v4; // ebx
  unsigned int v5; // r15d
  __int64 v6; // rdi
  u_short v7; // ax
  bool v8; // zf
  int v9; // eax
  u_long v10; // eax
  size_t v11; // r8
  _BYTE v13[548]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 v14; // [rsp+244h] [rbp+144h]
  char Src[106]; // [rsp+246h] [rbp+146h] BYREF
  _BYTE v16[608]; // [rsp+2B0h] [rbp+1B0h] BYREF
  int v17; // [rsp+520h] [rbp+420h] BYREF
  __int64 v18; // [rsp+528h] [rbp+428h] BYREF

  v18 = 0;
  memset_0(v16, 0, 0x238u);
  memset_0(v13, 0, 0x290u);
  v17 = 0;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_(1028, 27, WPP_8483b35a6c81311e7498c1c8b1f5bcb4_Traceguids);
  if ( a1 )
    *a1 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a1 && a2 )
  {
    v4 = Dhcpv6EnumPhyInftAddress(&v17, v16, v13);
    if ( !v4 )
    {
      v5 = v14 + 8;
      v18 = DhcpAlloc(v5);
      v6 = v18;
      if ( v18 )
      {
        v4 = 0;
        v7 = htons(1u);
        v8 = g_fVelocityFixDuidHardwareType == 0;
        *(_WORD *)v6 = v7;
        if ( v8 )
          *(_BYTE *)(v6 + 2) = v17;
        else
          *(_WORD *)(v6 + 2) = htons(v17);
        v9 = _time64(0);
        v10 = htonl(v9 - 946751400);
        v11 = v14;
        *(_DWORD *)(v6 + 4) = v10;
        memcpy_0((void *)(v6 + 8), Src, v11);
        *a2 = v6;
        *a1 = v5;
        v18 = 0;
      }
      else
      {
        v4 = 8;
      }
    }
  }
  else
  {
    v4 = 87;
  }
  DhcpFree(&v18);
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 28, WPP_8483b35a6c81311e7498c1c8b1f5bcb4_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18001dabc  mov     [rsp-8+arg_10], rbx
0x18001dac1  push    rbp
0x18001dac2  push    rsi
0x18001dac3  push    rdi
0x18001dac4  push    r14
0x18001dac6  push    r15
0x18001dac8  lea     rbp, [rsp-3F0h]
0x18001dad0  sub     rsp, 4F0h
0x18001dad7  mov     rsi, rdx
0x18001dada  mov     [rbp+410h+arg_8], 0
0x18001dae5  mov     r14, rcx
0x18001dae8  xor     edx, edx; Val
0x18001daea  lea     rcx, [rbp+410h+var_260]; void *
0x18001daf1  mov     r8d, 238h; Size
0x18001daf7  call    memset_0
0x18001dafc  xor     edx, edx; Val
0x18001dafe  lea     rcx, [rsp+510h+var_4F0]; void *
0x18001db03  mov     r8d, 290h; Size
0x18001db09  call    memset_0
0x18001db0e  mov     [rbp+410h+arg_0], 0
0x18001db18  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001db1f  jz      short loc_18001DB37
0x18001db21  mov     edx, 1Bh
0x18001db26  lea     r8, WPP_8483b35a6c81311e7498c1c8b1f5bcb4_Traceguids
0x18001db2d  mov     ecx, 404h
0x18001db32  call    WPP_SF_
0x18001db37  test    r14, r14
0x18001db3a  jz      short loc_18001DB43
0x18001db3c  mov     dword ptr [r14], 0
0x18001db43  test    rsi, rsi
0x18001db46  jz      short loc_18001DB4F
0x18001db48  mov     qword ptr [rsi], 0
0x18001db4f  test    r14, r14
0x18001db52  jnz     short loc_18001DB5E
0x18001db54  mov     ebx, 57h ; 'W'
0x18001db59  jmp     loc_18001DC36
0x18001db5e  test    rsi, rsi
0x18001db61  jz      short loc_18001DB54
0x18001db63  lea     r8, [rsp+510h+var_4F0]
0x18001db68  lea     rdx, [rbp+410h+var_260]
0x18001db6f  lea     rcx, [rbp+410h+arg_0]
0x18001db76  call    Dhcpv6EnumPhyInftAddress
0x18001db7b  mov     ebx, eax
0x18001db7d  test    eax, eax
0x18001db7f  jnz     loc_18001DC36
0x18001db85  movzx   r15d, [rbp+410h+var_2CC]
0x18001db8d  add     r15d, 8
0x18001db91  mov     ecx, r15d
0x18001db94  call    DhcpAlloc
0x18001db99  mov     [rbp+410h+arg_8], rax
0x18001dba0  mov     rdi, rax
0x18001dba3  test    rax, rax
0x18001dba6  jnz     short loc_18001DBB0
0x18001dba8  lea     ebx, [rax+8]
0x18001dbab  jmp     loc_18001DC36
0x18001dbb0  xor     ebx, ebx
0x18001dbb2  lea     ecx, [rbx+1]; hostshort
0x18001dbb5  call    cs:__imp_htons
0x18001dbbc  nop     dword ptr [rax+rax+00h]
0x18001dbc1  cmp     cs:g_fVelocityFixDuidHardwareType, ebx
0x18001dbc7  mov     [rdi], ax
0x18001dbca  jz      short loc_18001DBE5
0x18001dbcc  movzx   ecx, word ptr [rbp+410h+arg_0]; hostshort
0x18001dbd3  call    cs:__imp_htons
0x18001dbda  nop     dword ptr [rax+rax+00h]
0x18001dbdf  mov     [rdi+2], ax
0x18001dbe3  jmp     short loc_18001DBEE
0x18001dbe5  mov     al, byte ptr [rbp+410h+arg_0]
0x18001dbeb  mov     [rdi+2], al
0x18001dbee  xor     ecx, ecx; Time
0x18001dbf0  call    cs:__imp__time64
0x18001dbf7  nop     dword ptr [rax+rax+00h]
0x18001dbfc  lea     ecx, [rax-386E47A8h]; hostlong
0x18001dc02  call    cs:__imp_htonl
0x18001dc09  nop     dword ptr [rax+rax+00h]
0x18001dc0e  movzx   r8d, [rbp+410h+var_2CC]; Size
0x18001dc16  lea     rcx, [rdi+8]; void *
0x18001dc1a  lea     rdx, [rbp+410h+Src]; Src
0x18001dc21  mov     [rdi+4], eax
0x18001dc24  call    memcpy_0
0x18001dc29  mov     [rsi], rdi
0x18001dc2c  mov     [r14], r15d
0x18001dc2f  mov     [rbp+410h+arg_8], rbx
0x18001dc36  lea     rcx, [rbp+410h+arg_8]
0x18001dc3d  call    DhcpFree
0x18001dc42  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001dc49  jz      short loc_18001DC64
0x18001dc4b  mov     edx, 1Ch
0x18001dc50  lea     r8, WPP_8483b35a6c81311e7498c1c8b1f5bcb4_Traceguids
0x18001dc57  mov     ecx, 404h
0x18001dc5c  mov     r9d, ebx
0x18001dc5f  call    WPP_SF_D
0x18001dc64  mov     eax, ebx
0x18001dc66  mov     rbx, [rsp+510h+arg_10]
0x18001dc6e  add     rsp, 4F0h
0x18001dc75  pop     r15
0x18001dc77  pop     r14
0x18001dc79  pop     rdi
0x18001dc7a  pop     rsi
0x18001dc7b  pop     rbp
0x18001dc7c  retn
```
