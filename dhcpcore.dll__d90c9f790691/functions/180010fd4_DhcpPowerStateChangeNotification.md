# DhcpPowerStateChangeNotification

- ea: `0x180010fd4`
- end: `0x180011065`
- name: `DhcpPowerStateChangeNotification`
- size: `145`
- prototype: `__int64 __fastcall(int, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180021b40`

## callees

- `0x180010fd4`
- `0x18001cef0`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180011018`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180011018`

## pseudocode

```c
__int64 __fastcall DhcpPowerStateChangeNotification(int a1, _DWORD *a2)
{
  unsigned int v3; // edi
  int v4; // ecx
  GUID Source2; // [rsp+20h] [rbp-28h] BYREF

  Source2 = GUID_LOW_POWER_EPOCH;
  if ( a2 )
  {
    v3 = 0;
    if ( a1 == 32787 && RtlCompareMemory(a2, &Source2, 0x10u) == 16 && a2[4] == 4 )
    {
      v4 = a2[5];
      if ( v4 )
      {
        if ( v4 == 1 )
          DhcpGlobalIsInCS = 1;
      }
      else
      {
        DhcpGlobalIsInCS = 0;
      }
    }
  }
  else
  {
    return 87;
  }
  return v3;
}

```

## disassembly

```asm
0x180010fd4  mov     [rsp+arg_0], rbx
0x180010fd9  push    rdi
0x180010fda  sub     rsp, 40h
0x180010fde  mov     rax, cs:__security_cookie
0x180010fe5  xor     rax, rsp
0x180010fe8  mov     [rsp+48h+var_18], rax
0x180010fed  mov     rbx, rdx
0x180010ff0  movups  xmm0, xmmword ptr cs:GUID_LOW_POWER_EPOCH.Data1
0x180010ff7  movdqu  [rsp+48h+Source2], xmm0
0x180010ffd  test    rdx, rdx
0x180011000  jz      short loc_180011056
0x180011002  xor     edi, edi
0x180011004  cmp     ecx, 8013h
0x18001100a  jnz     short loc_18001103C
0x18001100c  lea     r8d, [rdi+10h]; Length
0x180011010  mov     rcx, rbx; Source1
0x180011013  lea     rdx, [rsp+48h+Source2]; Source2
0x180011018  call    cs:__imp_RtlCompareMemory
0x18001101e  cmp     rax, 10h
0x180011022  jnz     short loc_18001103C
0x180011024  cmp     dword ptr [rbx+10h], 4
0x180011028  jnz     short loc_18001103C
0x18001102a  mov     ecx, [rbx+14h]
0x18001102d  test    ecx, ecx
0x18001102f  jz      short loc_18001105D
0x180011031  cmp     ecx, 1
0x180011034  jnz     short loc_18001103C
0x180011036  mov     cs:DhcpGlobalIsInCS, ecx
0x18001103c  mov     eax, edi
0x18001103e  mov     rcx, [rsp+48h+var_18]
0x180011043  xor     rcx, rsp; StackCookie
0x180011046  call    __security_check_cookie
0x18001104b  mov     rbx, [rsp+48h+arg_0]
0x180011050  add     rsp, 40h
0x180011054  pop     rdi
0x180011055  retn
0x180011056  mov     edi, 57h ; 'W'
0x18001105b  jmp     short loc_18001103C
0x18001105d  mov     cs:DhcpGlobalIsInCS, edi
0x180011063  jmp     short loc_18001103C
```
