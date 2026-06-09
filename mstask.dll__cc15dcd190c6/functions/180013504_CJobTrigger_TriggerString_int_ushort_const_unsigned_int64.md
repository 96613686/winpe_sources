# CJobTrigger::TriggerString(int,ushort * const,unsigned __int64)

- ea: `0x180013504`
- end: `0x18001359b`
- name: `?TriggerString@CJobTrigger@@QEAAPEAGHQEAG_K@Z`
- size: `151`
- prototype: `unsigned __int16 *(CJobTrigger *__hidden this, int, unsigned __int16 *const, unsigned __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014328`
- `0x180014aa0`
- `0x180016b70`

## callees

- `0x180006f90`
- `0x180008688`
- `0x18000ca54`
- `0x180013504`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013582`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013582`

## pseudocode

```c
unsigned __int16 *__fastcall CJobTrigger::TriggerString(CJobTrigger *this, int a2, unsigned __int16 *const a3)
{
  signed int v6; // eax
  LPVOID pv; // [rsp+48h] [rbp+20h] BYREF

  pv = 0;
  v6 = StringFromTrigger((struct _TASK_TRIGGER *const)((char *)this + 24), (unsigned __int16 **)&pv, 0);
  *a3 = 0;
  if ( v6 >= 0 )
  {
    if ( a2 == 1 )
      StringCchPrintfW(a3, 0x200u, L"%d. ", (*((_WORD *)this + 13) & 0x7FFFu) + 1);
    StringCchCatW(a3, 0x200u, (const unsigned __int16 *)pv);
    CoTaskMemFree(pv);
  }
  return a3;
}

```

## disassembly

```asm
0x180013504  mov     rax, rsp
0x180013507  mov     [rax+8], rbx
0x18001350b  mov     [rax+10h], rsi
0x18001350f  mov     [rax+20h], r9
0x180013513  push    rdi
0x180013514  sub     rsp, 20h
0x180013518  mov     rbx, r8
0x18001351b  mov     qword ptr [rax+20h], 0
0x180013523  mov     edi, edx
0x180013525  mov     rsi, rcx
0x180013528  add     rcx, 18h; struct _TASK_TRIGGER *
0x18001352c  lea     rdx, [rax+20h]; unsigned __int16 **
0x180013530  xor     r8d, r8d; struct _SHELLDETAILS *
0x180013533  call    ?StringFromTrigger@@YAJQEAU_TASK_TRIGGER@@PEAPEAGPEAU_SHELLDETAILS@@@Z; StringFromTrigger(_TASK_TRIGGER * const,ushort * *,_SHELLDETAILS *)
0x180013538  xor     r9d, r9d
0x18001353b  mov     [rbx], r9w
0x18001353f  test    eax, eax
0x180013541  js      short loc_180013588
0x180013543  cmp     edi, 1
0x180013546  jnz     short loc_18001356B
0x180013548  movzx   r9d, word ptr [rsi+1Ah]
0x18001354d  lea     r8, aD_0; "%d. "
0x180013554  and     r9d, 7FFFh
0x18001355b  mov     edx, 200h; unsigned __int64
0x180013560  inc     r9d
0x180013563  mov     rcx, rbx; unsigned __int16 *
0x180013566  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001356b  mov     r8, [rsp+28h+pv]; unsigned __int16 *
0x180013570  mov     edx, 200h; unsigned __int64
0x180013575  mov     rcx, rbx; unsigned __int16 *
0x180013578  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001357d  mov     rcx, [rsp+28h+pv]; pv
0x180013582  call    cs:__imp_CoTaskMemFree
0x180013588  mov     rsi, [rsp+28h+arg_8]
0x18001358d  mov     rax, rbx
0x180013590  mov     rbx, [rsp+28h+arg_0]
0x180013595  add     rsp, 20h
0x180013599  pop     rdi
0x18001359a  retn
```
