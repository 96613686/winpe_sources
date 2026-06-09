# FF_DumpProcess(void)

- ea: `0x1400036d0`
- end: `0x1400037a4`
- name: `?FF_DumpProcess@@YAXXZ`
- size: `212`
- prototype: `void __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140003fec`

## callees

- `0x1400036d0`
- `0x1400037ac`
- `0x140004640`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400036ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400036ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003793`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003793`

## string_xrefs

- `0x14000375e`: `com\complus\src\shared\util\svcerr.cpp`

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
  if ( dword_140010678 )
  {
    EnterCriticalSection(&CriticalSection);
    v1 = 1;
  }
  if ( !dword_14000F2F0 )
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
      dword_14000F2F0 = 1;
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
0x1400036d0  mov     [rsp-8+arg_0], rbx
0x1400036d5  push    rbp
0x1400036d6  mov     rbp, rsp
0x1400036d9  sub     rsp, 50h
0x1400036dd  xor     ebx, ebx
0x1400036df  cmp     cs:dword_140010678, ebx
0x1400036e5  jz      short loc_1400036F9
0x1400036e7  lea     rcx, CriticalSection; lpCriticalSection
0x1400036ee  call    cs:__imp_EnterCriticalSection
0x1400036f4  mov     ebx, 1
0x1400036f9  cmp     cs:dword_14000F2F0, 0
0x140003700  jnz     loc_140003788
0x140003706  xor     eax, eax
0x140003708  mov     cs:FileName, ax
0x14000370f  call    ?FF_DumpProcess_MD@@YAJPEAG@Z; FF_DumpProcess_MD(ushort *)
0x140003714  test    eax, eax
0x140003716  jnz     short loc_140003734
0x140003718  mov     cs:dword_14000F2F0, 1
0x140003722  mov     r8d, 4C5h
0x140003728  mov     [rbp+var_30], eax
0x14000372b  mov     [rbp+var_28], 40000309h
0x140003732  jmp     short loc_140003746
0x140003734  jns     short loc_140003788
0x140003736  mov     [rbp+var_30], eax
0x140003739  mov     r8d, 4C9h; unsigned int
0x14000373f  mov     [rbp+var_28], 4000030Ah
0x140003746  mov     eax, 28h ; '('
0x14000374b  mov     [rbp+var_18], 0
0x140003753  lea     r9, FileName; unsigned __int16 *
0x14000375a  mov     [rbp+var_2C], ax
0x14000375e  lea     rdx, aComComplusSrcS_0; "com\\complus\\src\\shared\\util\\svcerr"...
0x140003765  mov     [rbp+var_20], r9
0x140003769  lea     rcx, [rbp+var_30]; this
0x14000376d  mov     [rbp+var_10], 0
0x140003775  mov     [rbp+var_8], 0
0x14000377c  mov     [rbp+var_4], 1
0x140003783  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x140003788  test    ebx, ebx
0x14000378a  jz      short loc_140003799
0x14000378c  lea     rcx, CriticalSection; lpCriticalSection
0x140003793  call    cs:__imp_LeaveCriticalSection
0x140003799  mov     rbx, [rsp+50h+arg_0]
0x14000379e  add     rsp, 50h
0x1400037a2  pop     rbp
0x1400037a3  retn
```
