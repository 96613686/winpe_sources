# NTEventLog::AuditSecurityEvent(ushort,ulong,ushort,_AUDIT_PARAM *)

- ea: `0x1800150c0`
- end: `0x1800150f9`
- name: `?AuditSecurityEvent@NTEventLog@@UEAAJGKGPEAU_AUDIT_PARAM@@@Z`
- size: `57`
- prototype: `__int64 __fastcall(NTEventLog *__hidden this, unsigned __int16, unsigned int, unsigned __int16, struct _AUDIT_PARAM *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800150c0`
- `0x1800154e0`

## pseudocode

```c
__int64 __fastcall NTEventLog::AuditSecurityEvent(
        NTEventLog *this,
        unsigned __int16 a2,
        unsigned int a3,
        unsigned __int16 a4,
        struct _AUDIT_PARAM *a5)
{
  __int64 v5; // r11

  v5 = 3;
  if ( a2 == 6272 )
  {
    v5 = 1;
  }
  else if ( a2 == 6273 )
  {
    v5 = 2;
  }
  if ( *((_DWORD *)this + v5 + 4) )
    return CSecurityLogHelper::LogSecurityEvent((LPCRITICAL_SECTION)((char *)this + 32), a2, a3, a4, a5);
  else
    return 0;
}

```

## disassembly

```asm
0x1800150c0  movzx   r10d, dx
0x1800150c4  mov     r11d, 3
0x1800150ca  sub     r10d, 1880h
0x1800150d1  jz      short loc_1800150DF
0x1800150d3  cmp     r10d, 1
0x1800150d7  jnz     short loc_1800150E5
0x1800150d9  lea     r11d, [r10+1]
0x1800150dd  jmp     short loc_1800150E5
0x1800150df  mov     r11d, 1
0x1800150e5  cmp     dword ptr [rcx+r11*4+10h], 0
0x1800150eb  jnz     short loc_1800150F0
0x1800150ed  xor     eax, eax
0x1800150ef  retn
0x1800150f0  add     rcx, 20h ; ' '; lpCriticalSection
0x1800150f4  jmp     ?LogSecurityEvent@CSecurityLogHelper@@QEAAJGKGPEAU_AUDIT_PARAM@@@Z; CSecurityLogHelper::LogSecurityEvent(ushort,ulong,ushort,_AUDIT_PARAM *)
```
