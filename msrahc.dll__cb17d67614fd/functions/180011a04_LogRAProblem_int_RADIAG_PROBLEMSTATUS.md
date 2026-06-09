# LogRAProblem(int,_RADIAG_PROBLEMSTATUS)

- ea: `0x180011a04`
- end: `0x180011af2`
- name: `?LogRAProblem@@YAXHW4_RADIAG_PROBLEMSTATUS@@@Z`
- size: `238`
- prototype: `int __fastcall(int, int)`
- caller_count: `9`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000c998`
- `0x18000cb0c`
- `0x18000cc10`
- `0x18000ccd0`
- `0x18000cdf8`
- `0x18000ceb0`
- `0x18000da10`
- `0x18000e4d0`
- `0x18000ebe0`

## callees

- `0x180011a04`
- `0x18001223c`
- `0x1800148c4`
- `0x18001a5e0`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x180011aa3`
- `ADVAPI32!EventWrite` at `0x180011aa3`
- `KERNEL32!GetProcessHeap` at `0x180011ac4`
- `KERNEL32!GetProcessHeap` at `0x180011ac4`
- `KERNEL32!HeapFree` at `0x180011ad4`
- `KERNEL32!HeapFree` at `0x180011ad4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall LogRAProblem(int a1, int a2)
{
  int result; // eax
  CEventLogger *v5; // rcx
  int v6; // ebx
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  __int64 *v10; // rdx
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+20h] [rbp-38h] BYREF
  int v13; // [rsp+28h] [rbp-30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-28h] BYREF

  lpMem = 0;
  result = StringCchCopyWithAlloc((unsigned __int16 **)&lpMem, a2, a1);
  if ( result >= 0 )
  {
    v6 = a2 - 1;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( !v7 )
      {
        UserData.Ptr = (ULONGLONG)&v13;
        v13 = a1;
        *(_QWORD *)&UserData.Size = 4;
        result = EventWrite(g_Logger, &RADIAG_Problem_Rejected, 1u, &UserData);
        goto LABEL_13;
      }
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          if ( v9 != 1 )
            goto LABEL_13;
          v10 = RADIAG_Problem_Repair_Failed;
        }
        else
        {
          v10 = RADIAG_Problem_Repair_Success;
        }
      }
      else
      {
        v10 = RADIAG_Problem_Repair_Start;
      }
    }
    else
    {
      v10 = (__int64 *)&RADIAG_Problem_Confirmed;
    }
    result = CEventLogger::LogEvent(v5, (const struct _EVENT_DESCRIPTOR *)v10, (unsigned __int16 *)lpMem);
LABEL_13:
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      return HeapFree(ProcessHeap, 0, lpMem);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180011a04  mov     [rsp+arg_8], rbx
0x180011a09  push    rsi
0x180011a0a  sub     rsp, 50h
0x180011a0e  mov     rax, cs:__security_cookie
0x180011a15  xor     rax, rsp
0x180011a18  mov     [rsp+58h+var_18], rax
0x180011a1d  mov     esi, ecx
0x180011a1f  mov     [rsp+58h+lpMem], 0
0x180011a28  mov     r8d, ecx; int
0x180011a2b  mov     ebx, edx
0x180011a2d  lea     rcx, [rsp+58h+lpMem]; unsigned __int16 **
0x180011a32  call    ?StringCchCopyWithAlloc@@YAJPEAPEAGHH@Z; StringCchCopyWithAlloc(ushort * *,int,int)
0x180011a37  test    eax, eax
0x180011a39  js      loc_180011ADA
0x180011a3f  sub     ebx, 1
0x180011a42  jz      short loc_180011AAB
0x180011a44  sub     ebx, 1
0x180011a47  jz      short loc_180011A73
0x180011a49  sub     ebx, 1
0x180011a4c  jz      short loc_180011A6A
0x180011a4e  sub     ebx, 1
0x180011a51  jz      short loc_180011A61
0x180011a53  cmp     ebx, 1
0x180011a56  jnz     short loc_180011ABC
0x180011a58  lea     rdx, RADIAG_Problem_Repair_Failed
0x180011a5f  jmp     short loc_180011AB2
0x180011a61  lea     rdx, RADIAG_Problem_Repair_Success
0x180011a68  jmp     short loc_180011AB2
0x180011a6a  lea     rdx, RADIAG_Problem_Repair_Start
0x180011a71  jmp     short loc_180011AB2
0x180011a73  mov     rcx, cs:?g_Logger@@3VCEventLogger@@A; RegHandle
0x180011a7a  lea     rax, [rsp+58h+var_30]
0x180011a7f  lea     r9, [rsp+58h+UserData]; UserData
0x180011a84  mov     [rsp+58h+UserData.Ptr], rax
0x180011a89  mov     r8d, 1; UserDataCount
0x180011a8f  mov     [rsp+58h+var_30], esi
0x180011a93  lea     rdx, RADIAG_Problem_Rejected; EventDescriptor
0x180011a9a  mov     qword ptr [rsp+58h+UserData.Size], 4
0x180011aa3  call    cs:__imp_EventWrite
0x180011aa9  jmp     short loc_180011ABC
0x180011aab  lea     rdx, RADIAG_Problem_Confirmed; struct _EVENT_DESCRIPTOR *
0x180011ab2  mov     r8, [rsp+58h+lpMem]; unsigned __int16 *
0x180011ab7  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,ushort *)
0x180011abc  cmp     [rsp+58h+lpMem], 0
0x180011ac2  jz      short loc_180011ADA
0x180011ac4  call    cs:__imp_GetProcessHeap
0x180011aca  mov     r8, [rsp+58h+lpMem]; lpMem
0x180011acf  xor     edx, edx; dwFlags
0x180011ad1  mov     rcx, rax; hHeap
0x180011ad4  call    cs:__imp_HeapFree
0x180011ada  mov     rcx, [rsp+58h+var_18]
0x180011adf  xor     rcx, rsp; StackCookie
0x180011ae2  call    __security_check_cookie
0x180011ae7  mov     rbx, [rsp+58h+arg_8]
0x180011aec  add     rsp, 50h
0x180011af0  pop     rsi
0x180011af1  retn
```
