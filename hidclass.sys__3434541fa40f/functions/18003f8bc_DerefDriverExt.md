# DerefDriverExt

- ea: `0x18003f8bc`
- end: `0x18003f979`
- name: `DerefDriverExt`
- size: `189`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18003a590`
- `0x18003b0a0`
- `0x18003b444`
- `0x18003b69c`
- `0x18003f634`
- `0x18003f830`

## callees

- `0x18001d2f8`
- `0x18003f8bc`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x18003f8d7`
- `ntoskrnl!ExAcquireFastMutex` at `0x18003f8d7`
- `ntoskrnl!ExReleaseFastMutex` at `0x18003f914`
- `ntoskrnl!ExReleaseFastMutex` at `0x18003f914`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003f964`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003f964`

## pseudocode

```c
_VPB **__fastcall DerefDriverExt(_VPB *a1)
{
  _VPB **v2; // rdi
  struct _DEVICE_OBJECT *p_Queue; // rdx
  _VPB **p_Vpb; // rbx
  __int64 v7; // rax
  _DRIVER_OBJECT *DriverObject; // rcx
  _VPB *v9; // rcx

  v2 = 0;
  ExAcquireFastMutex((PFAST_MUTEX)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
  p_Queue = (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Queue;
  while ( 1 )
  {
    p_Queue = *(struct _DEVICE_OBJECT **)&p_Queue->Type;
    if ( p_Queue == (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Queue )
      break;
    p_Vpb = &p_Queue[-1].Vpb;
    if ( p_Queue[-1].Vpb == a1 )
    {
      if ( --*((_DWORD *)p_Vpb + 68) < 0 )
      {
        v7 = *(_QWORD *)&p_Queue->Type;
        if ( *(struct _DEVICE_OBJECT **)(*(_QWORD *)&p_Queue->Type + 8LL) != p_Queue
          || (DriverObject = p_Queue->DriverObject, *(struct _DEVICE_OBJECT **)&DriverObject->Type != p_Queue) )
        {
          __fastfail(3u);
        }
        *(_QWORD *)&DriverObject->Type = v7;
        *(_QWORD *)(v7 + 8) = DriverObject;
        v9 = p_Vpb[2];
        if ( v9 )
          ExFreePoolWithTag(v9, 0);
      }
      v2 = p_Vpb;
      break;
    }
  }
  ExReleaseFastMutex((PFAST_MUTEX)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
  if ( !v2 )
    TraceLoggingDerefDriverExtFailed();
  return v2;
}

```

## disassembly

```asm
0x18003f8bc  mov     [rsp+arg_0], rbx
0x18003f8c1  mov     [rsp+arg_10], rsi
0x18003f8c6  push    rdi
0x18003f8c7  sub     rsp, 20h
0x18003f8cb  mov     rsi, rcx
0x18003f8ce  xor     edi, edi
0x18003f8d0  lea     rcx, WPP_MAIN_CB.Queue+10h; FastMutex
0x18003f8d7  call    cs:__imp_ExAcquireFastMutex
0x18003f8de  nop     dword ptr [rax+rax+00h]
0x18003f8e3  lea     rax, WPP_MAIN_CB.Queue
0x18003f8ea  mov     rdx, rax
0x18003f8ed  mov     rdx, [rdx]
0x18003f8f0  cmp     rdx, rax
0x18003f8f3  jz      short loc_18003F90D
0x18003f8f5  lea     rbx, [rdx-118h]
0x18003f8fc  cmp     [rbx], rsi
0x18003f8ff  jnz     short loc_18003F8ED
0x18003f901  sub     dword ptr [rbx+110h], 1
0x18003f908  js      short loc_18003F939
0x18003f90a  mov     rdi, rbx
0x18003f90d  lea     rcx, WPP_MAIN_CB.Queue+10h; FastMutex
0x18003f914  call    cs:__imp_ExReleaseFastMutex
0x18003f91b  nop     dword ptr [rax+rax+00h]
0x18003f920  test    rdi, rdi
0x18003f923  jz      short loc_18003F972
0x18003f925  mov     rbx, [rsp+28h+arg_0]
0x18003f92a  mov     rax, rdi
0x18003f92d  mov     rsi, [rsp+28h+arg_10]
0x18003f932  add     rsp, 20h
0x18003f936  pop     rdi
0x18003f937  retn
0x18003f939  mov     rax, [rdx]
0x18003f93c  cmp     [rax+8], rdx
0x18003f940  jnz     short loc_18003F94B
0x18003f942  mov     rcx, [rdx+8]
0x18003f946  cmp     [rcx], rdx
0x18003f949  jz      short loc_18003F952
0x18003f94b  mov     ecx, 3
0x18003f950  int     29h; Win8: RtlFailFast(ecx)
0x18003f952  mov     [rcx], rax
0x18003f955  mov     [rax+8], rcx
0x18003f959  mov     rcx, [rbx+10h]; P
0x18003f95d  test    rcx, rcx
0x18003f960  jz      short loc_18003F90A
0x18003f962  xor     edx, edx; Tag
0x18003f964  call    cs:__imp_ExFreePoolWithTag
0x18003f96b  nop     dword ptr [rax+rax+00h]
0x18003f970  jmp     short loc_18003F90A
0x18003f972  call    TraceLoggingDerefDriverExtFailed
0x18003f977  jmp     short loc_18003F925
```
