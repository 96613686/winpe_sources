# DriverFoundInDriverStore(void *,ushort *,PLATFORM,_FILETIME,unsigned __int64,_SP_DRVINFO_DATA_V2_W *,ushort *,ulong,int *)

- ea: `0x1800180f0`
- end: `0x180018256`
- name: `?DriverFoundInDriverStore@@YAJPEAXPEAGW4PLATFORM@@U_FILETIME@@_KPEAU_SP_DRVINFO_DATA_V2_W@@1KPEAH@Z`
- size: `358`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001a5e0`
- `0x18001b648`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180007944`
- `0x18000b200`
- `0x1800180f0`
- `0x1800272bc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800181ec`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800181ec`
- `KERNEL32!lstrcmpiW` at `0x180018184`
- `KERNEL32!lstrcmpiW` at `0x180018184`

## pseudocode

```c
__int64 __fastcall DriverFoundInDriverStore(
        __int64 a1,
        const WCHAR *a2,
        int a3,
        FILETIME a4,
        unsigned __int64 a5,
        __int64 a6,
        unsigned __int16 *a7,
        unsigned int a8,
        _DWORD *a9)
{
  int v10; // r15d
  int LastErrorAsFailHR; // ebx
  int v12; // edx
  NCoreLibrary *v13; // rcx
  LONG v14; // eax
  __int64 v16; // [rsp+30h] [rbp-268h] BYREF
  FILETIME FileTime1; // [rsp+38h] [rbp-260h] BYREF
  WCHAR ReturnBuffer[264]; // [rsp+40h] [rbp-258h] BYREF

  FileTime1 = a4;
  v10 = a1;
  if ( (unsigned __int64)(a1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && a2 && a6 && a7 && a8 && a9 )
  {
    LastErrorAsFailHR = 0;
    *a9 = 0;
    if ( !lstrcmpiW(a2, (LPCWSTR)(a6 + 16)) )
    {
      LODWORD(v16) = 0;
      memset_0(ReturnBuffer, 0, 0x208u);
      if ( (unsigned int)GetDriverStorePathFromDeviceInfo(v10, v12, a6, a3, (__int64)&v16, ReturnBuffer)
        || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v13), LastErrorAsFailHR >= 0) )
      {
        if ( (_DWORD)v16 )
        {
          v14 = CompareFileTime(&FileTime1, (const FILETIME *)(a6 + 1552));
          if ( v14 == -1 || !v14 && a5 <= *(_QWORD *)(a6 + 1560) )
          {
            LastErrorAsFailHR = StringCchCopyW(a7, a8, ReturnBuffer);
            if ( LastErrorAsFailHR >= 0 )
              *a9 = 1;
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)LastErrorAsFailHR;
}

```

## disassembly

```asm
0x1800180f0  push    rbx
0x1800180f2  push    rsi
0x1800180f3  push    rdi
0x1800180f4  push    r12
0x1800180f6  push    r14
0x1800180f8  push    r15
0x1800180fa  sub     rsp, 268h
0x180018101  mov     rax, cs:__security_cookie
0x180018108  xor     rax, rsp
0x18001810b  mov     [rsp+298h+var_48], rax
0x180018113  mov     rdi, [rsp+298h+arg_28]
0x18001811b  lea     rax, [rcx-1]
0x18001811f  mov     r14, [rsp+298h+arg_30]
0x180018127  mov     r12d, r8d
0x18001812a  mov     rsi, [rsp+298h+arg_40]
0x180018132  mov     r8, rdx
0x180018135  mov     qword ptr [rsp+298h+FileTime1.dwLowDateTime], r9
0x18001813a  mov     r15, rcx
0x18001813d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180018141  ja      loc_18001822E
0x180018147  test    rdx, rdx
0x18001814a  jz      loc_18001822E
0x180018150  test    rdi, rdi
0x180018153  jz      loc_18001822E
0x180018159  test    r14, r14
0x18001815c  jz      loc_18001822E
0x180018162  cmp     dword ptr [rsp+298h+arg_38], 0
0x18001816a  jbe     loc_18001822E
0x180018170  test    rsi, rsi
0x180018173  jz      loc_18001822E
0x180018179  xor     ebx, ebx
0x18001817b  lea     rdx, [rdi+10h]; lpString2
0x18001817f  mov     rcx, r8; lpString1
0x180018182  mov     [rsi], ebx
0x180018184  call    cs:__imp_lstrcmpiW
0x18001818a  test    eax, eax
0x18001818c  jnz     loc_180018233
0x180018192  xor     edx, edx; Val
0x180018194  mov     dword ptr [rsp+298h+var_268], ebx
0x180018198  mov     r8d, 208h; Size
0x18001819e  lea     rcx, [rsp+298h+var_258]; void *
0x1800181a3  call    memset_0
0x1800181a8  lea     rax, [rsp+298h+var_258]
0x1800181ad  mov     r9d, r12d; int
0x1800181b0  mov     [rsp+298h+ReturnBuffer], rax; ReturnBuffer
0x1800181b5  mov     r8, rdi; int
0x1800181b8  lea     rax, [rsp+298h+var_268]
0x1800181bd  mov     rcx, r15; int
0x1800181c0  mov     [rsp+298h+var_278], rax; __int64
0x1800181c5  call    GetDriverStorePathFromDeviceInfo
0x1800181ca  test    eax, eax
0x1800181cc  jnz     short loc_1800181D9
0x1800181ce  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x1800181d3  mov     ebx, eax
0x1800181d5  test    eax, eax
0x1800181d7  js      short loc_180018233
0x1800181d9  cmp     dword ptr [rsp+298h+var_268], 0
0x1800181de  jz      short loc_180018233
0x1800181e0  lea     rdx, [rdi+610h]; lpFileTime2
0x1800181e7  lea     rcx, [rsp+298h+FileTime1]; lpFileTime1
0x1800181ec  call    cs:__imp_CompareFileTime
0x1800181f2  cmp     eax, 0FFFFFFFFh
0x1800181f5  jz      short loc_18001820C
0x1800181f7  test    eax, eax
0x1800181f9  jnz     short loc_180018233
0x1800181fb  mov     rax, [rdi+618h]
0x180018202  cmp     [rsp+298h+arg_20], rax
0x18001820a  ja      short loc_180018233
0x18001820c  mov     edx, dword ptr [rsp+298h+arg_38]; unsigned __int64
0x180018213  lea     r8, [rsp+298h+var_258]; unsigned __int16 *
0x180018218  mov     rcx, r14; unsigned __int16 *
0x18001821b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018220  mov     ebx, eax
0x180018222  test    eax, eax
0x180018224  js      short loc_180018233
0x180018226  mov     dword ptr [rsi], 1
0x18001822c  jmp     short loc_180018233
0x18001822e  mov     ebx, 80070057h
0x180018233  mov     eax, ebx
0x180018235  mov     rcx, [rsp+298h+var_48]
0x18001823d  xor     rcx, rsp; StackCookie
0x180018240  call    __security_check_cookie
0x180018245  add     rsp, 268h
0x18001824c  pop     r15
0x18001824e  pop     r14
0x180018250  pop     r12
0x180018252  pop     rdi
0x180018253  pop     rsi
0x180018254  pop     rbx
0x180018255  retn
```
