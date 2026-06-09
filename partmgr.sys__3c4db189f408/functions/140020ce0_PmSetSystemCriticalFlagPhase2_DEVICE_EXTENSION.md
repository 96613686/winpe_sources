# PmSetSystemCriticalFlagPhase2(_DEVICE_EXTENSION *)

- ea: `0x140020ce0`
- end: `0x140020e0d`
- name: `?PmSetSystemCriticalFlagPhase2@@YAJPEAU_DEVICE_EXTENSION@@@Z`
- size: `301`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140007674`

## callees

- `0x140007bcc`
- `0x140020ce0`

## pseudocode

```c
__int64 __fastcall PmSetSystemCriticalFlagPhase2(KSPIN_LOCK *a1)
{
  _QWORD *DeviceExtension; // rdi
  int DriveLayout; // r10d
  int v4; // ecx
  unsigned int *v5; // rdx
  unsigned int v6; // r9d
  __int64 v7; // r8
  KSPIN_LOCK v8; // rax
  unsigned int *v9; // rdx
  unsigned int v10; // r9d
  __int64 v11; // r8
  KSPIN_LOCK v12; // rax

  DeviceExtension = PmControlObject->DeviceExtension;
  DriveLayout = PmGetDriveLayoutEx(a1, 0);
  if ( DriveLayout >= 0 )
  {
    v4 = *((_DWORD *)a1 + 228);
    if ( v4 )
    {
      if ( v4 == 1 )
      {
        v5 = (unsigned int *)DeviceExtension[24];
        if ( *v5 )
        {
          v6 = 0;
          do
          {
            v7 = 7LL * v6;
            if ( (v5[v7 + 7] & 0x40) == 0
              && v5[v7 + 1] == 1
              && *(_QWORD *)&v5[v7 + 3] == a1[115]
              && *(_QWORD *)&v5[v7 + 5] == a1[116] )
            {
              v8 = a1[1];
              *((_BYTE *)a1 + 604) = 1;
              *(_DWORD *)(a1[1] + 48) = v5[v7 + 7] | *(_DWORD *)(v8 + 48);
              v5[v7 + 7] |= 0x40u;
            }
            v5 = (unsigned int *)DeviceExtension[24];
            ++v6;
          }
          while ( v6 < *v5 );
        }
      }
    }
    else
    {
      v9 = (unsigned int *)DeviceExtension[24];
      if ( *v9 )
      {
        v10 = 0;
        do
        {
          v11 = 7LL * v10;
          if ( (v9[v11 + 7] & 0x40) == 0 && !v9[v11 + 1] && v9[v11 + 3] == *((_DWORD *)a1 + 230) )
          {
            v12 = a1[1];
            *((_BYTE *)a1 + 604) = 1;
            *(_DWORD *)(a1[1] + 48) = v9[v11 + 7] | *(_DWORD *)(v12 + 48);
            v9[v11 + 7] |= 0x40u;
          }
          v9 = (unsigned int *)DeviceExtension[24];
          ++v10;
        }
        while ( v10 < *v9 );
      }
    }
  }
  return (unsigned int)DriveLayout;
}

```

## disassembly

```asm
0x140020ce0  mov     [rsp+arg_0], rbx
0x140020ce5  push    rdi
0x140020ce6  sub     rsp, 20h
0x140020cea  mov     rax, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x140020cf1  xor     edx, edx; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x140020cf3  mov     rbx, rcx
0x140020cf6  mov     rdi, [rax+40h]
0x140020cfa  call    ?PmGetDriveLayoutEx@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmGetDriveLayoutEx(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX * *)
0x140020cff  xor     r11d, r11d
0x140020d02  mov     r10d, eax
0x140020d05  test    eax, eax
0x140020d07  js      loc_140020DFE
0x140020d0d  mov     ecx, [rbx+390h]
0x140020d13  test    ecx, ecx
0x140020d15  jz      loc_140020D9C
0x140020d1b  cmp     ecx, 1
0x140020d1e  jnz     loc_140020DFE
0x140020d24  mov     rdx, [rdi+0C0h]
0x140020d2b  cmp     [rdx], r11d
0x140020d2e  jbe     loc_140020DFE
0x140020d34  mov     r9d, r11d
0x140020d37  mov     eax, r9d
0x140020d3a  imul    r8, rax, 1Ch
0x140020d3e  mov     eax, [r8+rdx+1Ch]
0x140020d43  test    al, 40h
0x140020d45  jnz     short loc_140020D8B
0x140020d47  cmp     dword ptr [r8+rdx+4], 1
0x140020d4d  jnz     short loc_140020D8B
0x140020d4f  mov     rax, [r8+rdx+0Ch]
0x140020d54  cmp     rax, [rbx+398h]
0x140020d5b  jnz     short loc_140020D8B
0x140020d5d  mov     rax, [r8+rdx+14h]
0x140020d62  cmp     rax, [rbx+3A0h]
0x140020d69  jnz     short loc_140020D8B
0x140020d6b  mov     rax, [rbx+8]
0x140020d6f  mov     byte ptr [rbx+25Ch], 1
0x140020d76  mov     ecx, [rax+30h]
0x140020d79  mov     rax, [rbx+8]
0x140020d7d  or      ecx, [r8+rdx+1Ch]
0x140020d82  mov     [rax+30h], ecx
0x140020d85  or      dword ptr [r8+rdx+1Ch], 40h
0x140020d8b  mov     rdx, [rdi+0C0h]
0x140020d92  inc     r9d
0x140020d95  cmp     r9d, [rdx]
0x140020d98  jb      short loc_140020D37
0x140020d9a  jmp     short loc_140020DFE
0x140020d9c  mov     rdx, [rdi+0C0h]
0x140020da3  cmp     [rdx], r11d
0x140020da6  jbe     short loc_140020DFE
0x140020da8  mov     r9d, r11d
0x140020dab  mov     eax, r9d
0x140020dae  imul    r8, rax, 1Ch
0x140020db2  mov     eax, [r8+rdx+1Ch]
0x140020db7  test    al, 40h
0x140020db9  jnz     short loc_140020DEF
0x140020dbb  cmp     [r8+rdx+4], r11d
0x140020dc0  jnz     short loc_140020DEF
0x140020dc2  mov     eax, [rbx+398h]
0x140020dc8  cmp     [r8+rdx+0Ch], eax
0x140020dcd  jnz     short loc_140020DEF
0x140020dcf  mov     rax, [rbx+8]
0x140020dd3  mov     byte ptr [rbx+25Ch], 1
0x140020dda  mov     ecx, [rax+30h]
0x140020ddd  mov     rax, [rbx+8]
0x140020de1  or      ecx, [r8+rdx+1Ch]
0x140020de6  mov     [rax+30h], ecx
0x140020de9  or      dword ptr [r8+rdx+1Ch], 40h
0x140020def  mov     rdx, [rdi+0C0h]
0x140020df6  inc     r9d
0x140020df9  cmp     r9d, [rdx]
0x140020dfc  jb      short loc_140020DAB
0x140020dfe  mov     rbx, [rsp+28h+arg_0]
0x140020e03  mov     eax, r10d
0x140020e06  add     rsp, 20h
0x140020e0a  pop     rdi
0x140020e0b  retn
```
