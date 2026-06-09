# DpspReadQueuedResolutionsFromFile(void *)

- ea: `0x1800137a8`
- end: `0x180013900`
- name: `?DpspReadQueuedResolutionsFromFile@@YAJPEAX@Z`
- size: `344`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800152c4`

## callees

- `0x180005ec0`
- `0x180007adc`
- `0x180008f70`
- `0x180009090`
- `0x180013214`
- `0x1800137a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800137dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800137dc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013892`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013892`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800138bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800138bc`

## string_xrefs

- `0x180013809`: `DpspReadQueuedResolutionsFromFile`

## pseudocode

```c
__int64 __fastcall DpspReadQueuedResolutionsFromFile(HANDLE hFile)
{
  signed int LastError; // eax
  signed int Args; // ebx
  int v4; // r8d
  int v5; // eax
  int v6; // edi
  unsigned int Buffer; // [rsp+50h] [rbp+20h] BYREF
  int v9; // [rsp+58h] [rbp+28h] BYREF
  struct INSTANCEINFO *v10; // [rsp+60h] [rbp+30h] BYREF

  v9 = 0;
  Buffer = 0;
  v10 = 0;
  if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    goto LABEL_8;
  LastError = GetLastError();
  Args = LastError;
  if ( LastError > 0 )
    Args = (unsigned __int16)LastError | 0x80070000;
  if ( Args >= 0 )
  {
LABEL_8:
    v5 = WdipReadFile(hFile, (char *)&Buffer, 4u, &v9);
    Args = v5;
    if ( v5 >= 0 )
    {
      v6 = 0;
      if ( Buffer )
      {
        while ( 1 )
        {
          Args = DpspReadQueuedResolutionFromFile(hFile, &v10);
          if ( Args < 0 )
            break;
          if ( v10 )
          {
            Args = DpspQueueInstanceToUsers(*((PSID *)v10 + 95), v10);
            if ( Args < 0 )
            {
              DpspFreeSpecificInstanceInfo(&v10);
              v4 = 1647;
              v10 = 0;
              goto LABEL_6;
            }
            AcquireSRWLockExclusive(&g_SRWInstanceList);
            *((_QWORD *)v10 + 154) = g_pInstanceHead;
            g_pInstanceHead = (__int64)v10;
            ReleaseSRWLockExclusive(&g_SRWInstanceList);
            v10 = 0;
          }
          if ( ++v6 >= Buffer )
            return (unsigned int)Args;
        }
        return 0;
      }
    }
    else
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
        (int)L"DpspReadQueuedResolutionsFromFile",
        1625,
        (int)L"Error = %d",
        v5);
    }
  }
  else
  {
    v4 = 1617;
LABEL_6:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspReadQueuedResolutionsFromFile",
      v4,
      (int)L"Error = %d",
      Args);
  }
  return (unsigned int)Args;
}

```

## disassembly

```asm
0x1800137a8  mov     [rsp-18h+arg_18], rbx
0x1800137ad  push    rbp
0x1800137ae  push    rsi
0x1800137af  push    rdi
0x1800137b0  mov     rbp, rsp
0x1800137b3  sub     rsp, 30h
0x1800137b7  lea     rax, [rcx+1]
0x1800137bb  mov     [rbp+arg_8], 0
0x1800137c2  mov     [rbp+Buffer], 0
0x1800137c9  mov     rsi, rcx
0x1800137cc  mov     [rbp+arg_10], 0
0x1800137d4  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800137da  jnz     short loc_180013821
0x1800137dc  call    cs:__imp_GetLastError
0x1800137e2  mov     ebx, eax
0x1800137e4  test    eax, eax
0x1800137e6  jle     short loc_1800137F1
0x1800137e8  movzx   ebx, ax
0x1800137eb  or      ebx, 80070000h
0x1800137f1  test    ebx, ebx
0x1800137f3  jns     short loc_180013821
0x1800137f5  mov     r8d, 651h; int
0x1800137fb  movzx   eax, bx
0x1800137fe  mov     dword ptr [rsp+30h+Args], eax; Args
0x180013802  lea     r9, aErrorD; "Error = %d"
0x180013809  lea     rdx, aDpspreadqueued_0; "DpspReadQueuedResolutionsFromFile"
0x180013810  lea     rcx, aClientcoreBase_2; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180013817  call    WdipTraceError
0x18001381c  jmp     loc_1800138F1
0x180013821  lea     r9, [rbp+arg_8]
0x180013825  mov     r8d, 4; nNumberOfBytesToRead
0x18001382b  lea     rdx, [rbp+Buffer]; lpBuffer
0x18001382f  mov     rcx, rsi; hFile
0x180013832  call    WdipReadFile
0x180013837  mov     ebx, eax
0x180013839  test    eax, eax
0x18001383b  jns     short loc_18001384C
0x18001383d  movzx   ecx, ax
0x180013840  mov     r8d, 659h
0x180013846  mov     dword ptr [rsp+30h+Args], ecx
0x18001384a  jmp     short loc_180013802
0x18001384c  xor     edi, edi
0x18001384e  cmp     [rbp+Buffer], edi
0x180013851  jbe     loc_1800138F1
0x180013857  lea     rdx, [rbp+arg_10]; struct INSTANCEINFO **
0x18001385b  mov     rcx, rsi; hFile
0x18001385e  call    ?DpspReadQueuedResolutionFromFile@@YAJPEAXPEAPEAUINSTANCEINFO@@@Z; DpspReadQueuedResolutionFromFile(void *,INSTANCEINFO * *)
0x180013863  mov     ebx, eax
0x180013865  test    eax, eax
0x180013867  js      loc_1800138EF
0x18001386d  mov     rcx, [rbp+arg_10]
0x180013871  test    rcx, rcx
0x180013874  jz      short loc_1800138CA
0x180013876  mov     rdx, rcx; struct INSTANCEINFO *
0x180013879  mov     rcx, [rcx+2F8h]; pSid1
0x180013880  call    DpspQueueInstanceToUsers
0x180013885  mov     ebx, eax
0x180013887  test    eax, eax
0x180013889  js      short loc_1800138D3
0x18001388b  lea     rcx, g_SRWInstanceList; SRWLock
0x180013892  call    cs:__imp_AcquireSRWLockExclusive
0x180013898  mov     rcx, [rbp+arg_10]
0x18001389c  mov     rax, cs:g_pInstanceHead
0x1800138a3  mov     [rcx+4D0h], rax
0x1800138aa  lea     rcx, g_SRWInstanceList; SRWLock
0x1800138b1  mov     rax, [rbp+arg_10]
0x1800138b5  mov     cs:g_pInstanceHead, rax
0x1800138bc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800138c2  mov     [rbp+arg_10], 0
0x1800138ca  inc     edi
0x1800138cc  cmp     edi, [rbp+Buffer]
0x1800138cf  jb      short loc_180013857
0x1800138d1  jmp     short loc_1800138F1
0x1800138d3  lea     rcx, [rbp+arg_10]
0x1800138d7  call    DpspFreeSpecificInstanceInfo
0x1800138dc  mov     r8d, 66Fh
0x1800138e2  mov     [rbp+arg_10], 0
0x1800138ea  jmp     loc_1800137FB
0x1800138ef  xor     ebx, ebx
0x1800138f1  mov     eax, ebx
0x1800138f3  mov     rbx, [rsp+30h+arg_18]
0x1800138f8  add     rsp, 30h
0x1800138fc  pop     rdi
0x1800138fd  pop     rsi
0x1800138fe  pop     rbp
0x1800138ff  retn
```
