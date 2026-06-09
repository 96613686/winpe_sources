# PmSetPartitionFlags(_PARTITION_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *)

- ea: `0x14000d048`
- end: `0x14000d177`
- name: `?PmSetPartitionFlags@@YAXPEAU_PARTITION_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `303`
- prototype: `void __fastcall(struct _PARTITION_EXTENSION *, struct _DRIVE_LAYOUT_INFORMATION_EX *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400254c8`

## callees

- `0x14000cd18`
- `0x14000d048`

## pseudocode

```c
void __fastcall PmSetPartitionFlags(struct _PARTITION_EXTENSION *a1, struct _DRIVE_LAYOUT_INFORMATION_EX *a2)
{
  __int64 v3; // rcx
  _BYTE *DeviceExtension; // r8
  int v6; // ecx
  _DWORD *v7; // r10
  int v8; // r8d
  _DWORD *v9; // rdx
  _DWORD *v10; // r10
  int v11; // r8d
  unsigned int v12; // [rsp+30h] [rbp+8h] BYREF

  v12 = 0;
  v3 = *((_QWORD *)a1 + 3);
  if ( *(_BYTE *)(v3 + 604) )
  {
    DeviceExtension = PmControlObject->DeviceExtension;
    if ( DeviceExtension[440] )
    {
      if ( PmIsSystemCriticalFlagNeeded((struct _DEVICE_EXTENSION *)v3, (unsigned int *)a1 + 48, &v12) )
        *(_DWORD *)(*((_QWORD *)a1 + 1) + 48LL) |= v12;
      return;
    }
    v6 = *((_DWORD *)a1 + 42);
    if ( !v6 )
    {
      v10 = (_DWORD *)*((_QWORD *)DeviceExtension + 24);
      if ( !*v10 )
        return;
      v11 = 0;
      while ( 1 )
      {
        v9 = &v10[7 * v11 + 1];
        if ( !*v9 && v9[2] == a2->Mbr.Signature && v9[1] == *((_DWORD *)a1 + 48) )
          break;
        if ( (unsigned int)++v11 >= *v10 )
          return;
      }
      goto LABEL_22;
    }
    if ( v6 == 1 )
    {
      v7 = (_DWORD *)*((_QWORD *)DeviceExtension + 24);
      if ( *v7 )
      {
        v8 = 0;
        while ( 1 )
        {
          v9 = &v7[7 * v8 + 1];
          if ( *v9 == 1
            && *((_QWORD *)v9 + 1) == *(_QWORD *)&a2->Mbr.Signature
            && *((_QWORD *)v9 + 2) == *(_QWORD *)a2->Gpt.DiskId.Data4
            && v9[1] == *((_DWORD *)a1 + 48) )
          {
            break;
          }
          if ( (unsigned int)++v8 >= *v7 )
            return;
        }
LABEL_22:
        *(_DWORD *)(*((_QWORD *)a1 + 1) + 48LL) |= v9[6] & 0xFFFFFFBF;
      }
    }
  }
}

```

## disassembly

```asm
0x14000d048  push    rbx
0x14000d04a  sub     rsp, 20h
0x14000d04e  mov     rbx, rcx
0x14000d051  mov     [rsp+28h+arg_0], 0
0x14000d059  mov     rcx, [rcx+18h]; struct _DEVICE_EXTENSION *
0x14000d05d  mov     r11, rdx
0x14000d060  cmp     byte ptr [rcx+25Ch], 0
0x14000d067  jz      loc_14000D170
0x14000d06d  mov     rax, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x14000d074  mov     r8, [rax+40h]
0x14000d078  cmp     byte ptr [r8+1B8h], 0
0x14000d080  jz      short loc_14000D0B2
0x14000d082  lea     rdx, [rbx+0C0h]; unsigned int *
0x14000d089  lea     r8, [rsp+28h+arg_0]; unsigned int *
0x14000d08e  call    ?PmIsSystemCriticalFlagNeeded@@YAEPEAU_DEVICE_EXTENSION@@PEAK1@Z; PmIsSystemCriticalFlagNeeded(_DEVICE_EXTENSION *,ulong *,ulong *)
0x14000d093  test    al, al
0x14000d095  jz      loc_14000D170
0x14000d09b  mov     rax, [rbx+8]
0x14000d09f  mov     ecx, [rax+30h]
0x14000d0a2  mov     rax, [rbx+8]
0x14000d0a6  or      ecx, [rsp+28h+arg_0]
0x14000d0aa  mov     [rax+30h], ecx
0x14000d0ad  jmp     loc_14000D170
0x14000d0b2  mov     ecx, [rbx+0A8h]
0x14000d0b8  test    ecx, ecx
0x14000d0ba  jz      short loc_14000D117
0x14000d0bc  cmp     ecx, 1
0x14000d0bf  jnz     loc_14000D170
0x14000d0c5  mov     r10, [r8+0C0h]
0x14000d0cc  mov     r9d, [r10]
0x14000d0cf  test    r9d, r9d
0x14000d0d2  jz      loc_14000D170
0x14000d0d8  xor     r8d, r8d
0x14000d0db  mov     eax, r8d
0x14000d0de  imul    rdx, rax, 1Ch
0x14000d0e2  add     rdx, 4
0x14000d0e6  add     rdx, r10
0x14000d0e9  cmp     dword ptr [rdx], 1
0x14000d0ec  jnz     short loc_14000D10D
0x14000d0ee  mov     rax, [rdx+8]
0x14000d0f2  cmp     rax, [r11+8]
0x14000d0f6  jnz     short loc_14000D10D
0x14000d0f8  mov     rax, [rdx+10h]
0x14000d0fc  cmp     rax, [r11+10h]
0x14000d100  jnz     short loc_14000D10D
0x14000d102  mov     eax, [rbx+0C0h]
0x14000d108  cmp     [rdx+4], eax
0x14000d10b  jz      short loc_14000D15A
0x14000d10d  inc     r8d
0x14000d110  cmp     r8d, r9d
0x14000d113  jb      short loc_14000D0DB
0x14000d115  jmp     short loc_14000D170
0x14000d117  mov     r10, [r8+0C0h]
0x14000d11e  mov     r9d, [r10]
0x14000d121  test    r9d, r9d
0x14000d124  jz      short loc_14000D170
0x14000d126  xor     r8d, r8d
0x14000d129  mov     eax, r8d
0x14000d12c  imul    rdx, rax, 1Ch
0x14000d130  add     rdx, 4
0x14000d134  add     rdx, r10
0x14000d137  cmp     dword ptr [rdx], 0
0x14000d13a  jnz     short loc_14000D150
0x14000d13c  mov     eax, [r11+8]
0x14000d140  cmp     [rdx+8], eax
0x14000d143  jnz     short loc_14000D150
0x14000d145  mov     eax, [rbx+0C0h]
0x14000d14b  cmp     [rdx+4], eax
0x14000d14e  jz      short loc_14000D15A
0x14000d150  inc     r8d
0x14000d153  cmp     r8d, r9d
0x14000d156  jb      short loc_14000D129
0x14000d158  jmp     short loc_14000D170
0x14000d15a  mov     rax, [rbx+8]
0x14000d15e  mov     ecx, [rax+30h]
0x14000d161  mov     edx, [rdx+18h]
0x14000d164  mov     rax, [rbx+8]
0x14000d168  and     edx, 0FFFFFFBFh
0x14000d16b  or      edx, ecx
0x14000d16d  mov     [rax+30h], edx
0x14000d170  add     rsp, 20h
0x14000d174  pop     rbx
0x14000d175  retn
```
