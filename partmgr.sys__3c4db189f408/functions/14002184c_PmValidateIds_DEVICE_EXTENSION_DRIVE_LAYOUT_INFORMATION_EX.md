# PmValidateIds(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *)

- ea: `0x14002184c`
- end: `0x140021969`
- name: `?PmValidateIds@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _DRIVE_LAYOUT_INFORMATION_EX *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x140005b2c`

## callees

- `0x14000ab3c`
- `0x14000d6f4`
- `0x1400214fc`
- `0x14002184c`

## pseudocode

```c
__int64 __fastcall PmValidateIds(struct _DEVICE_EXTENSION *a1, struct _DRIVE_LAYOUT_INFORMATION_EX *a2)
{
  struct _DRIVE_LAYOUT_INFORMATION_EX *v2; // rdi
  struct _DEVICE_EXTENSION *v3; // rbx
  _DWORD *DeviceExtension; // rsi
  int v5; // r8d
  unsigned int updated; // edx
  __int128 v8; // [rsp+20h] [rbp-30h] BYREF
  __int128 v9; // [rsp+30h] [rbp-20h]
  __int64 v10; // [rsp+40h] [rbp-10h]
  unsigned __int8 v11; // [rsp+80h] [rbp+30h] BYREF
  int v12; // [rsp+88h] [rbp+38h] BYREF

  v12 = 0;
  v10 = 0;
  v2 = a2;
  v3 = a1;
  v11 = 0;
  v8 = 0;
  DeviceExtension = PmControlObject->DeviceExtension;
  v9 = 0;
  while ( 1 )
  {
    updated = PmCheckIds(a1, a2, &v11, (enum _DISK_OFFLINE_REASON *)&v12);
    if ( (updated & 0x80000000) != 0 )
      break;
    v5 = v12;
    if ( v12 )
    {
      if ( v12 == 2 )
      {
        *((_QWORD *)&v8 + 1) = 3;
        *(_QWORD *)&v9 = 3;
      }
      else
      {
        if ( v12 != 4 || (*((_QWORD *)v3 + 66) & 0x20) != 0 )
          return updated;
        if ( DeviceExtension[41] == 2 )
        {
          if ( (unsigned int)(*(_DWORD *)(*((_QWORD *)v3 + 29) + 28LL) - 15) <= 1 )
            return updated;
        }
        else if ( DeviceExtension[41] == 3 )
        {
          return updated;
        }
        *((_QWORD *)&v8 + 1) = 1;
        *(_QWORD *)&v9 = 1;
      }
    }
    else if ( !v11 )
    {
      return updated;
    }
    if ( v12 )
    {
      *((_BYTE *)v3 + 604) = 0;
      LODWORD(v8) = 40;
      BYTE4(v8) = 0;
      return (unsigned int)PmSetDiskAttributes((__int64)v3, (__int64)&v8, v5);
    }
    updated = PmUpdateIds(v3, v2);
    if ( (updated & 0x80000000) != 0 )
      return updated;
    a2 = v2;
    a1 = v3;
  }
  return updated;
}

```

## disassembly

```asm
0x14002184c  mov     [rsp-18h+arg_0], rbx
0x140021851  push    rbp
0x140021852  push    rsi
0x140021853  push    rdi
0x140021854  mov     rbp, rsp
0x140021857  sub     rsp, 50h
0x14002185b  xor     eax, eax
0x14002185d  mov     [rbp+arg_18], 0
0x140021864  xorps   xmm0, xmm0
0x140021867  mov     [rbp+var_10], rax
0x14002186b  mov     rax, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x140021872  mov     rdi, rdx
0x140021875  mov     rbx, rcx
0x140021878  mov     [rbp+arg_10], 0
0x14002187c  movups  [rbp+var_30], xmm0
0x140021880  mov     rsi, [rax+40h]
0x140021884  movups  [rbp+var_20], xmm0
0x140021888  jmp     loc_140021923
0x14002188d  mov     r8d, [rbp+arg_18]
0x140021891  test    r8d, r8d
0x140021894  jz      short loc_140021901
0x140021896  cmp     r8d, 2
0x14002189a  jz      short loc_1400218EF
0x14002189c  cmp     r8d, 4
0x1400218a0  jnz     loc_140021959
0x1400218a6  mov     rax, [rbx+210h]
0x1400218ad  test    al, 20h
0x1400218af  jnz     loc_140021959
0x1400218b5  mov     ecx, [rsi+0A4h]
0x1400218bb  sub     ecx, 2
0x1400218be  jz      short loc_1400218CB
0x1400218c0  cmp     ecx, 1
0x1400218c3  jz      loc_140021959
0x1400218c9  jmp     short loc_1400218DD
0x1400218cb  mov     rax, [rbx+0E8h]
0x1400218d2  mov     ecx, [rax+1Ch]
0x1400218d5  sub     ecx, 0Fh
0x1400218d8  cmp     ecx, 1
0x1400218db  jbe     short loc_140021959
0x1400218dd  mov     qword ptr [rbp+var_30+8], 1
0x1400218e5  mov     qword ptr [rbp+var_20], 1
0x1400218ed  jmp     short loc_140021907
0x1400218ef  mov     qword ptr [rbp+var_30+8], 3
0x1400218f7  mov     qword ptr [rbp+var_20], 3
0x1400218ff  jmp     short loc_140021907
0x140021901  cmp     [rbp+arg_10], 0
0x140021905  jz      short loc_140021959
0x140021907  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x14002190a  test    r8d, r8d
0x14002190d  jnz     short loc_14002193C
0x14002190f  mov     rdx, rdi; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140021912  call    ?PmUpdateIds@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmUpdateIds(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x140021917  mov     edx, eax
0x140021919  test    eax, eax
0x14002191b  js      short loc_140021959
0x14002191d  mov     rdx, rdi; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140021920  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x140021923  lea     r9, [rbp+arg_18]; enum _DISK_OFFLINE_REASON *
0x140021927  lea     r8, [rbp+arg_10]; unsigned __int8 *
0x14002192b  call    ?PmCheckIds@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAEPEAW4_DISK_OFFLINE_REASON@@@Z; PmCheckIds(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,uchar *,_DISK_OFFLINE_REASON *)
0x140021930  mov     edx, eax
0x140021932  test    eax, eax
0x140021934  jns     loc_14002188D
0x14002193a  jmp     short loc_140021959
0x14002193c  lea     rdx, [rbp+var_30]
0x140021940  mov     byte ptr [rbx+25Ch], 0
0x140021947  mov     dword ptr [rbp+var_30], 28h ; '('
0x14002194e  mov     byte ptr [rbp+var_30+4], 0
0x140021952  call    ?PmSetDiskAttributes@@YAJPEAU_DEVICE_EXTENSION@@PEAU_SET_DISK_ATTRIBUTES@@W4_DISK_OFFLINE_REASON@@@Z; PmSetDiskAttributes(_DEVICE_EXTENSION *,_SET_DISK_ATTRIBUTES *,_DISK_OFFLINE_REASON)
0x140021957  mov     edx, eax
0x140021959  mov     rbx, [rsp+50h+arg_0]
0x14002195e  mov     eax, edx
0x140021960  add     rsp, 50h
0x140021964  pop     rdi
0x140021965  pop     rsi
0x140021966  pop     rbp
0x140021967  retn
```
