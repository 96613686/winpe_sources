# PmIoctlDsmQuerySectorWrite(_IRP *,uchar *,__int64 *,unsigned __int64 *)

- ea: `0x14001d894`
- end: `0x14001d9e5`
- name: `?PmIoctlDsmQuerySectorWrite@@YAJPEAU_IRP@@PEAEPEA_JPEA_K@Z`
- size: `337`
- prototype: `__int64 __fastcall(struct _IRP *, unsigned __int8 *, __int64 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400087c0`
- `0x14001ed38`

## callees

- `0x14001d894`
- `0x140023cb4`

## pseudocode

```c
__int64 __fastcall PmIoctlDsmQuerySectorWrite(struct _IRP *a1, unsigned __int8 *a2, __int64 *a3, unsigned __int64 *a4)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  unsigned int Options; // r10d
  unsigned int v9; // edx
  int *p_Type; // rcx
  unsigned int v11; // r11d
  unsigned int v12; // eax
  __int64 v13; // rcx
  __int64 *v14; // r8
  __int64 v15; // rcx
  __int64 v16; // r9
  __int64 v17; // r10
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v21; // [rsp+70h] [rbp+8h] BYREF

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  v21 = 0;
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( Options < 0x1C )
    return (unsigned int)-1073741811;
  p_Type = (int *)&a1->AssociatedIrp.MasterIrp->Type;
  v9 = 0;
  v11 = p_Type[6];
  if ( v11 )
  {
    if ( (p_Type[2] & 1) != 0 )
      return (unsigned int)-1073741811;
    v12 = p_Type[5];
    if ( !v12 || (v11 & 0xF) != 0 || v12 < 0x1C )
      return (unsigned int)-1073741811;
    if ( v12 + v11 < v12 )
      return (unsigned int)-1073741675;
    if ( v12 + v11 > Options )
      return (unsigned int)-1073741811;
    v9 = 0;
  }
  if ( p_Type[1] < 0 )
    goto LABEL_16;
  if ( (p_Type[2] & 1) != 0 )
  {
    v9 = PmSendDeviceControl(CurrentStackLocation->DeviceObject, 0x7405Cu, 0, 0, &v21, 8u, 0);
    if ( (v9 & 0x80000000) != 0 )
      return v9;
    v13 = v21;
    *a3 = 0;
LABEL_30:
    *a2 = 1;
    *a4 = v13;
    return v9;
  }
  if ( !v11 )
  {
LABEL_16:
    *a2 = 0;
    return v9;
  }
  v14 = (__int64 *)((char *)p_Type + (unsigned int)p_Type[5]);
  if ( ((unsigned __int8)v14 & 7) == 0 )
  {
    v15 = 0;
    v16 = 0x7FFFFFFFFFFFFFFFLL;
    while ( v11 >= 0x10 )
    {
      v17 = *v14;
      v18 = *v14;
      if ( *v14 >= v16 )
        v18 = v16;
      v16 = v18;
      if ( v17 < 0 )
        return (unsigned int)-1073741811;
      v19 = v17 + v14[1];
      if ( v19 < (unsigned __int64)v17 || v19 < 0 )
        return (unsigned int)-1073741675;
      if ( v19 > v15 )
        v15 = v19 - 1;
      v14 += 2;
      v11 -= 16;
      v9 = 0;
    }
    *a3 = v16;
    v13 = v15 - v16 + 1;
    goto LABEL_30;
  }
  return (unsigned int)-1073741811;
}

```

## disassembly

```asm
0x14001d894  push    rbx
0x14001d896  push    rsi
0x14001d897  push    rdi
0x14001d898  push    r14
0x14001d89a  sub     rsp, 48h
0x14001d89e  mov     rdi, [rcx+0B8h]
0x14001d8a5  mov     rsi, r9
0x14001d8a8  mov     [rsp+68h+arg_0], 0
0x14001d8b1  mov     r14, r8
0x14001d8b4  mov     rbx, rdx
0x14001d8b7  mov     r10d, [rdi+10h]
0x14001d8bb  cmp     r10d, 1Ch
0x14001d8bf  jnb     short loc_14001D8CB
0x14001d8c1  mov     edx, 0C000000Dh
0x14001d8c6  jmp     loc_14001D9D8
0x14001d8cb  mov     rcx, [rcx+18h]
0x14001d8cf  xor     edx, edx
0x14001d8d1  mov     r11d, [rcx+18h]
0x14001d8d5  test    r11d, r11d
0x14001d8d8  jz      short loc_14001D906
0x14001d8da  mov     eax, [rcx+8]
0x14001d8dd  test    al, 1
0x14001d8df  jnz     short loc_14001D8C1
0x14001d8e1  mov     eax, [rcx+14h]
0x14001d8e4  test    eax, eax
0x14001d8e6  jz      short loc_14001D8C1
0x14001d8e8  test    r11b, 0Fh
0x14001d8ec  jnz     short loc_14001D8C1
0x14001d8ee  cmp     eax, 1Ch
0x14001d8f1  jb      short loc_14001D8C1
0x14001d8f3  lea     edx, [rax+r11]
0x14001d8f7  cmp     edx, eax
0x14001d8f9  jb      loc_14001D9C2
0x14001d8ff  cmp     edx, r10d
0x14001d902  ja      short loc_14001D8C1
0x14001d904  xor     edx, edx
0x14001d906  cmp     dword ptr [rcx+4], 0
0x14001d90a  jl      short loc_14001D95B
0x14001d90c  mov     eax, [rcx+8]
0x14001d90f  test    al, 1
0x14001d911  jz      short loc_14001D956
0x14001d913  mov     rcx, [rdi+28h]; DeviceObject
0x14001d917  lea     rax, [rsp+68h+arg_0]
0x14001d91c  mov     [rsp+68h+var_38], 0; BOOLEAN
0x14001d921  xor     r9d, r9d; InputBufferLength
0x14001d924  mov     [rsp+68h+var_40], 8; ULONG
0x14001d92c  xor     r8d, r8d; InputBuffer
0x14001d92f  mov     edx, 7405Ch; IoControlCode
0x14001d934  mov     [rsp+68h+var_48], rax; PVOID
0x14001d939  call    ?PmSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; PmSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x14001d93e  mov     edx, eax
0x14001d940  test    eax, eax
0x14001d942  js      loc_14001D9D8
0x14001d948  mov     rcx, [rsp+68h+arg_0]
0x14001d94d  mov     qword ptr [r14], 0
0x14001d954  jmp     short loc_14001D9D2
0x14001d956  test    r11d, r11d
0x14001d959  jnz     short loc_14001D960
0x14001d95b  mov     byte ptr [rbx], 0
0x14001d95e  jmp     short loc_14001D9D8
0x14001d960  mov     r8d, [rcx+14h]
0x14001d964  add     r8, rcx
0x14001d967  test    r8b, 7
0x14001d96b  jnz     loc_14001D8C1
0x14001d971  xor     ecx, ecx
0x14001d973  mov     r9, 7FFFFFFFFFFFFFFFh
0x14001d97d  cmp     r11d, 10h
0x14001d981  jb      short loc_14001D9C9
0x14001d983  mov     r10, [r8]
0x14001d986  cmp     r10, r9
0x14001d989  mov     rax, r10
0x14001d98c  cmovge  rax, r9
0x14001d990  mov     r9, rax
0x14001d993  test    r10, r10
0x14001d996  js      loc_14001D8C1
0x14001d99c  mov     rdx, [r8+8]
0x14001d9a0  add     rdx, r10
0x14001d9a3  cmp     rdx, r10
0x14001d9a6  jb      short loc_14001D9C2
0x14001d9a8  test    rdx, rdx
0x14001d9ab  js      short loc_14001D9C2
0x14001d9ad  cmp     rdx, rcx
0x14001d9b0  jle     short loc_14001D9B6
0x14001d9b2  lea     rcx, [rdx-1]
0x14001d9b6  add     r8, 10h
0x14001d9ba  add     r11d, 0FFFFFFF0h
0x14001d9be  xor     edx, edx
0x14001d9c0  jmp     short loc_14001D97D
0x14001d9c2  mov     edx, 0C0000095h
0x14001d9c7  jmp     short loc_14001D9D8
0x14001d9c9  sub     rcx, r9
0x14001d9cc  mov     [r14], r9
0x14001d9cf  inc     rcx
0x14001d9d2  mov     byte ptr [rbx], 1
0x14001d9d5  mov     [rsi], rcx
0x14001d9d8  mov     eax, edx
0x14001d9da  add     rsp, 48h
0x14001d9de  pop     r14
0x14001d9e0  pop     rdi
0x14001d9e1  pop     rsi
0x14001d9e2  pop     rbx
0x14001d9e3  retn
```
