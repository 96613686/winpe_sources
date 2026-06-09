# BthServPoliciesUpdatedCallback(void *)

- ea: `0x18001dd10`
- end: `0x18001dd52`
- name: `?BthServPoliciesUpdatedCallback@@YAXPEAX@Z`
- size: `66`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18001dd10`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001dd40`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001dd40`

## pseudocode

```c
void __fastcall BthServPoliciesUpdatedCallback(void *a1)
{
  struct _FILETIME pftDueTime; // [rsp+38h] [rbp+10h] BYREF

  pftDueTime = (struct _FILETIME)-1000000LL;
  if ( !byte_180047138 )
  {
    byte_180047138 = 1;
    SetThreadpoolTimer(pti, &pftDueTime, 0, 0);
  }
}

```

## disassembly

```asm
0x18001dd10  sub     rsp, 28h
0x18001dd14  mov     al, cs:byte_180047138
0x18001dd1a  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFFFF0BDC0h
0x18001dd23  test    al, al
0x18001dd25  jnz     short loc_18001DD4C
0x18001dd27  mov     rcx, cs:pti; pti
0x18001dd2e  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18001dd33  xor     r9d, r9d; msWindowLength
0x18001dd36  mov     cs:byte_180047138, 1
0x18001dd3d  xor     r8d, r8d; msPeriod
0x18001dd40  call    cs:__imp_SetThreadpoolTimer
0x18001dd47  nop     dword ptr [rax+rax+00h]
0x18001dd4c  add     rsp, 28h
0x18001dd50  retn
```
