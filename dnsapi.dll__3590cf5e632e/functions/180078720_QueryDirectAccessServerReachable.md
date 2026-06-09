# QueryDirectAccessServerReachable

- ea: `0x180078720`
- end: `0x180078929`
- name: `QueryDirectAccessServerReachable`
- size: `521`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18002b050`
- `0x18002e894`
- `0x1800317e0`
- `0x18004a0b0`
- `0x180078720`
- `0x1800dc9e0`
- `0x1800de650`
- `0x1800e4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800787a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800787e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800787a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800787e0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800788ea`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180078902`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800788ea`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180078902`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800787c8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800787c8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180078898`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180078898`

## string_xrefs

- `0x1800788c2`: `QueryDirectAccessServerReachable`

## pseudocode

```c
__int64 __fastcall QueryDirectAccessServerReachable(_WORD *Parameter)
{
  __int64 QueryBlob; // rsi
  DWORD v4; // edi
  HANDLE EventW; // rax
  DWORD LastError; // eax
  unsigned __int64 v7; // rax
  void *v8; // rcx
  HMODULE v9; // rcx
  HMODULE v10; // rcx

  if ( !Parameter )
    return 87;
  if ( *((_QWORD *)Parameter + 68) && *((_QWORD *)Parameter + 69) )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_(1035, 44, WPP_85172e4714023e67c3665ec5069963d4_Traceguids);
    QueryBlob = Query_AllocateQueryBlob(18);
    if ( QueryBlob )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      *(_QWORD *)(QueryBlob + 1168) = EventW;
      if ( EventW )
      {
        *(_QWORD *)(QueryBlob + 232) = Parameter;
        *(_QWORD *)(QueryBlob + 240) = Parameter;
        v4 = 0;
        *(_QWORD *)(QueryBlob + 248) = Parameter;
        *(_WORD *)(QueryBlob + 256) = Parameter[256];
        *(_QWORD *)(QueryBlob + 264) = *((_QWORD *)Parameter + 65) & 0xFFFFFFFFFFFFBFFFuLL;
        v7 = *((_QWORD *)Parameter + 65) & 0xFFFFFFFFFFFFBFFFuLL;
        *(_DWORD *)(QueryBlob + 392) = 36;
        *(_QWORD *)(QueryBlob + 600) = v7;
        *(_QWORD *)(QueryBlob + 1128) = *((_QWORD *)Parameter + 69);
        (*((void (__fastcall **)(__int64))Parameter + 68))(QueryBlob);
        WaitForSingleObject(*(HANDLE *)(QueryBlob + 1168), 0xFFFFFFFF);
        v8 = *(void **)(QueryBlob + 960);
        if ( v8 )
        {
          Dns_RecordListFree(v8);
          *(_QWORD *)(QueryBlob + 960) = 0;
        }
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_d(1035, 46, WPP_85172e4714023e67c3665ec5069963d4_Traceguids, LastError);
      }
      DeRefQueryBlobEx((LPVOID)QueryBlob);
    }
    else
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_(1035, 45, WPP_85172e4714023e67c3665ec5069963d4_Traceguids);
      v4 = GetLastError();
    }
  }
  else
  {
    v4 = 87;
  }
  v9 = (HMODULE)*((_QWORD *)Parameter + 66);
  if ( v9 )
    FreeLibrary(v9);
  v10 = (HMODULE)*((_QWORD *)Parameter + 67);
  if ( v10 )
    FreeLibrary(v10);
  DnsApiFree(Parameter);
  return v4;
}

```

## disassembly

```asm
0x180078720  mov     [rsp+arg_0], rbx
0x180078725  mov     [rsp+arg_8], rsi
0x18007872a  push    rdi
0x18007872b  sub     rsp, 20h
0x18007872f  mov     rbx, rcx
0x180078732  test    rcx, rcx
0x180078735  jnz     short loc_18007873F
0x180078737  lea     eax, [rcx+57h]
0x18007873a  jmp     loc_180078918
0x18007873f  cmp     qword ptr [rcx+220h], 0
0x180078747  jz      loc_1800788D9
0x18007874d  cmp     qword ptr [rcx+228h], 0
0x180078755  jz      loc_1800788D9
0x18007875b  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180078762  jz      short loc_18007877A
0x180078764  mov     edx, 2Ch ; ','
0x180078769  lea     r8, WPP_85172e4714023e67c3665ec5069963d4_Traceguids
0x180078770  mov     ecx, 40Bh
0x180078775  call    WPP_SF_
0x18007877a  mov     ecx, 12h
0x18007877f  call    Query_AllocateQueryBlob
0x180078784  mov     rsi, rax
0x180078787  test    rax, rax
0x18007878a  jnz     short loc_1800787BC
0x18007878c  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180078793  jz      short loc_1800787A9
0x180078795  lea     edx, [rax+2Dh]
0x180078798  mov     ecx, 40Bh
0x18007879d  lea     r8, WPP_85172e4714023e67c3665ec5069963d4_Traceguids
0x1800787a4  call    WPP_SF_
0x1800787a9  call    cs:__imp_GetLastError
0x1800787b0  nop     dword ptr [rax+rax+00h]
0x1800787b5  mov     edi, eax
0x1800787b7  jmp     loc_1800788DE
0x1800787bc  xor     r9d, r9d; lpName
0x1800787bf  xor     r8d, r8d; bInitialState
0x1800787c2  xor     ecx, ecx; lpEventAttributes
0x1800787c4  lea     edx, [r9+1]; bManualReset
0x1800787c8  call    cs:__imp_CreateEventW
0x1800787cf  nop     dword ptr [rax+rax+00h]
0x1800787d4  mov     [rsi+490h], rax
0x1800787db  test    rax, rax
0x1800787de  jnz     short loc_180078819
0x1800787e0  call    cs:__imp_GetLastError
0x1800787e7  nop     dword ptr [rax+rax+00h]
0x1800787ec  mov     edi, eax
0x1800787ee  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800787f5  jz      loc_1800788BC
0x1800787fb  mov     edx, 2Eh ; '.'
0x180078800  lea     r8, WPP_85172e4714023e67c3665ec5069963d4_Traceguids
0x180078807  mov     ecx, 40Bh
0x18007880c  mov     r9d, eax
0x18007880f  call    WPP_SF_d
0x180078814  jmp     loc_1800788BC
0x180078819  mov     [rsi+0E8h], rbx
0x180078820  mov     rcx, 0FFFFFFFFFFFFBFFFh
0x180078827  mov     [rsi+0F0h], rbx
0x18007882e  xor     edi, edi
0x180078830  mov     [rsi+0F8h], rbx
0x180078837  movzx   eax, word ptr [rbx+200h]
0x18007883e  mov     [rsi+100h], ax
0x180078845  mov     rax, [rbx+208h]
0x18007884c  and     rax, rcx
0x18007884f  mov     [rsi+108h], rax
0x180078856  mov     rax, [rbx+208h]
0x18007885d  and     rax, rcx
0x180078860  mov     dword ptr [rsi+188h], 24h ; '$'
0x18007886a  mov     [rsi+258h], rax
0x180078871  mov     rcx, rsi
0x180078874  mov     rax, [rbx+228h]
0x18007887b  mov     [rsi+468h], rax
0x180078882  mov     rax, [rbx+220h]
0x180078889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007888e  mov     rcx, [rsi+490h]; hHandle
0x180078895  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180078898  call    cs:__imp_WaitForSingleObject
0x18007889f  nop     dword ptr [rax+rax+00h]
0x1800788a4  mov     rcx, [rsi+3C0h]; lpMem
0x1800788ab  test    rcx, rcx
0x1800788ae  jz      short loc_1800788BC
0x1800788b0  call    Dns_RecordListFree
0x1800788b5  mov     [rsi+3C0h], rdi
0x1800788bc  mov     r9d, 12h
0x1800788c2  lea     rdx, aQuerydirectacc; "QueryDirectAccessServerReachable"
0x1800788c9  mov     r8d, 0E62h
0x1800788cf  mov     rcx, rsi; lpMem
0x1800788d2  call    DeRefQueryBlobEx
0x1800788d7  jmp     short loc_1800788DE
0x1800788d9  mov     edi, 57h ; 'W'
0x1800788de  mov     rcx, [rbx+210h]; hLibModule
0x1800788e5  test    rcx, rcx
0x1800788e8  jz      short loc_1800788F6
0x1800788ea  call    cs:__imp_FreeLibrary
0x1800788f1  nop     dword ptr [rax+rax+00h]
0x1800788f6  mov     rcx, [rbx+218h]; hLibModule
0x1800788fd  test    rcx, rcx
0x180078900  jz      short loc_18007890E
0x180078902  call    cs:__imp_FreeLibrary
0x180078909  nop     dword ptr [rax+rax+00h]
0x18007890e  mov     rcx, rbx; lpMem
0x180078911  call    DnsApiFree
0x180078916  mov     eax, edi
0x180078918  mov     rbx, [rsp+28h+arg_0]
0x18007891d  mov     rsi, [rsp+28h+arg_8]
0x180078922  add     rsp, 20h
0x180078926  pop     rdi
0x180078927  retn
```
