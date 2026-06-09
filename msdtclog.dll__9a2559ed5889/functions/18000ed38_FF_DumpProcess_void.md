# FF_DumpProcess(void)

- ea: `0x18000ed38`
- end: `0x18000ee0c`
- name: `?FF_DumpProcess@@YAXXZ`
- size: `212`
- prototype: `void __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f654`

## callees

- `0x18000ed38`
- `0x18000ee14`
- `0x18000fca8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000edfb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000edfb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ed56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ed56`

## string_xrefs

- `0x18000edc6`: `com\complus\src\shared\util\svcerr.cpp`

## pseudocode

```c
void __fastcall FF_DumpProcess(unsigned __int16 *a1)
{
  int v1; // ebx
  int v2; // eax
  unsigned int v3; // r8d
  int v4; // [rsp+20h] [rbp-30h] BYREF
  __int16 v5; // [rsp+24h] [rbp-2Ch]
  int v6; // [rsp+28h] [rbp-28h]
  wchar_t *v7; // [rsp+30h] [rbp-20h]
  __int64 v8; // [rsp+38h] [rbp-18h]
  __int64 v9; // [rsp+40h] [rbp-10h]
  int v10; // [rsp+48h] [rbp-8h]
  int v11; // [rsp+4Ch] [rbp-4h]

  v1 = 0;
  if ( dword_18001F938 )
  {
    EnterCriticalSection(&CriticalSection);
    v1 = 1;
  }
  if ( !dword_1800204C0 )
  {
    FileName = 0;
    v2 = FF_DumpProcess_MD(a1);
    if ( v2 )
    {
      if ( v2 >= 0 )
        goto LABEL_9;
      v4 = v2;
      v3 = 1225;
      v6 = 1073742602;
    }
    else
    {
      dword_1800204C0 = 1;
      v3 = 1221;
      v4 = 0;
      v6 = 1073742601;
    }
    v8 = 0;
    v5 = 40;
    v7 = &FileName;
    v9 = 0;
    v10 = 0;
    v11 = 1;
    CError::WriteToLog((CError *)&v4, L"com\\complus\\src\\shared\\util\\svcerr.cpp", v3, &FileName);
  }
LABEL_9:
  if ( v1 )
    LeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x18000ed38  mov     [rsp-8+arg_0], rbx
0x18000ed3d  push    rbp
0x18000ed3e  mov     rbp, rsp
0x18000ed41  sub     rsp, 50h
0x18000ed45  xor     ebx, ebx
0x18000ed47  cmp     cs:dword_18001F938, ebx
0x18000ed4d  jz      short loc_18000ED61
0x18000ed4f  lea     rcx, CriticalSection; lpCriticalSection
0x18000ed56  call    cs:__imp_EnterCriticalSection
0x18000ed5c  mov     ebx, 1
0x18000ed61  cmp     cs:dword_1800204C0, 0
0x18000ed68  jnz     loc_18000EDF0
0x18000ed6e  xor     eax, eax
0x18000ed70  mov     cs:FileName, ax
0x18000ed77  call    ?FF_DumpProcess_MD@@YAJPEAG@Z; FF_DumpProcess_MD(ushort *)
0x18000ed7c  test    eax, eax
0x18000ed7e  jnz     short loc_18000ED9C
0x18000ed80  mov     cs:dword_1800204C0, 1
0x18000ed8a  mov     r8d, 4C5h
0x18000ed90  mov     [rbp+var_30], eax
0x18000ed93  mov     [rbp+var_28], 40000309h
0x18000ed9a  jmp     short loc_18000EDAE
0x18000ed9c  jns     short loc_18000EDF0
0x18000ed9e  mov     [rbp+var_30], eax
0x18000eda1  mov     r8d, 4C9h; unsigned int
0x18000eda7  mov     [rbp+var_28], 4000030Ah
0x18000edae  mov     eax, 28h ; '('
0x18000edb3  mov     [rbp+var_18], 0
0x18000edbb  lea     r9, FileName; unsigned __int16 *
0x18000edc2  mov     [rbp+var_2C], ax
0x18000edc6  lea     rdx, aComComplusSrcS_0; "com\\complus\\src\\shared\\util\\svcerr"...
0x18000edcd  mov     [rbp+var_20], r9
0x18000edd1  lea     rcx, [rbp+var_30]; this
0x18000edd5  mov     [rbp+var_10], 0
0x18000eddd  mov     [rbp+var_8], 0
0x18000ede4  mov     [rbp+var_4], 1
0x18000edeb  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000edf0  test    ebx, ebx
0x18000edf2  jz      short loc_18000EE01
0x18000edf4  lea     rcx, CriticalSection; lpCriticalSection
0x18000edfb  call    cs:__imp_LeaveCriticalSection
0x18000ee01  mov     rbx, [rsp+50h+arg_0]
0x18000ee06  add     rsp, 50h
0x18000ee0a  pop     rbp
0x18000ee0b  retn
```
