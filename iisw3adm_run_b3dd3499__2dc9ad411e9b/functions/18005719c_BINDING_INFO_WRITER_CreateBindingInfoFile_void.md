# BINDING_INFO_WRITER::CreateBindingInfoFile(void)

- ea: `0x18005719c`
- end: `0x180057316`
- name: `?CreateBindingInfoFile@BINDING_INFO_WRITER@@AEAAJXZ`
- size: `378`
- prototype: `__int64 __fastcall(BINDING_INFO_WRITER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x18005740c`

## callees

- `0x18005719c`
- `0x18006101a`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800572b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800572b4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800572d5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800572d5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800572a4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800572a4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800572f2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800572f2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180057222`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180057222`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180057255`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180057271`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180057255`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180057271`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800571e5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800571e5`

## pseudocode

```c
__int64 __fastcall BINDING_INFO_WRITER::CreateBindingInfoFile(BINDING_INFO_WRITER *this)
{
  __int64 v2; // rdx
  const unsigned __int16 *v3; // rdx
  signed int v4; // ebx
  int v5; // edi
  HANDLE FileW; // rax
  signed int LastError; // eax
  _BYTE v9[32]; // [rsp+40h] [rbp-288h] BYREF
  LPCWSTR lpFileName; // [rsp+60h] [rbp-268h]
  int v11; // [rsp+70h] [rbp-258h]
  unsigned __int16 v12[264]; // [rsp+80h] [rbp-248h] BYREF

  memset_0(v12, 0, 0x208u);
  STRU::STRU((STRU *)v9, v12, 0x104u);
  v2 = *((_QWORD *)g_pWebAdminService + 229);
  if ( v2 && (v3 = *(const unsigned __int16 **)(v2 + 128)) != 0 && *v3 )
  {
    v4 = STRU::Copy((STRU *)v9, v3);
    if ( v4 >= 0 )
    {
      if ( !v11 || lpFileName[v11 - 1] == 92 || (v4 = STRU::Append((STRU *)v9, L"\\"), v4 >= 0) )
      {
        v4 = STRU::Append((STRU *)v9, L"bindingInfo.tmp");
        if ( v4 >= 0 )
        {
          v5 = 0;
          while ( 1 )
          {
            FileW = CreateFileW(lpFileName, 0x40000000u, 0, 0, 2u, 0x8000080u, 0);
            *((_QWORD *)this + 1) = FileW;
            if ( FileW != (HANDLE)-1LL )
              break;
            LastError = GetLastError();
            if ( LastError > 0 )
              v4 = (unsigned __int16)LastError | 0x80070000;
            else
              v4 = LastError;
            if ( LastError == 32 )
            {
              Sleep(0xC8u);
              if ( (unsigned int)++v5 < 0xA )
                continue;
            }
            goto LABEL_19;
          }
          v4 = 0;
        }
      }
    }
  }
  else
  {
    v4 = -2147024883;
  }
LABEL_19:
  STRU::~STRU((STRU *)v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18005719c  push    rbx
0x18005719e  push    rbp
0x18005719f  push    rsi
0x1800571a0  push    rdi
0x1800571a1  sub     rsp, 2A8h
0x1800571a8  mov     rax, cs:__security_cookie
0x1800571af  xor     rax, rsp
0x1800571b2  mov     [rsp+2C8h+var_38], rax
0x1800571ba  mov     rsi, rcx
0x1800571bd  xor     edx, edx; Val
0x1800571bf  lea     rcx, [rsp+2C8h+var_248]; void *
0x1800571c7  mov     r8d, 208h; Size
0x1800571cd  call    memset_0
0x1800571d2  mov     r8d, 104h
0x1800571d8  lea     rdx, [rsp+2C8h+var_248]
0x1800571e0  lea     rcx, [rsp+2C8h+var_288]
0x1800571e5  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800571eb  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x1800571f2  xor     ebp, ebp
0x1800571f4  mov     rdx, [rax+728h]
0x1800571fb  test    rdx, rdx
0x1800571fe  jz      loc_1800572E8
0x180057204  mov     rdx, [rdx+80h]
0x18005720b  test    rdx, rdx
0x18005720e  jz      loc_1800572E8
0x180057214  cmp     [rdx], bp
0x180057217  jz      loc_1800572E8
0x18005721d  lea     rcx, [rsp+2C8h+var_288]
0x180057222  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180057228  mov     ebx, eax
0x18005722a  test    eax, eax
0x18005722c  js      loc_1800572ED
0x180057232  mov     eax, [rsp+2C8h+var_258]
0x180057236  test    eax, eax
0x180057238  jz      short loc_180057265
0x18005723a  lea     ecx, [rax-1]
0x18005723d  mov     rax, [rsp+2C8h+lpFileName]
0x180057242  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x180057247  jz      short loc_180057265
0x180057249  lea     rdx, asc_180065770; "\\"
0x180057250  lea     rcx, [rsp+2C8h+var_288]
0x180057255  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18005725b  mov     ebx, eax
0x18005725d  test    eax, eax
0x18005725f  js      loc_1800572ED
0x180057265  lea     rdx, aBindinginfoTmp; "bindingInfo.tmp"
0x18005726c  lea     rcx, [rsp+2C8h+var_288]
0x180057271  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180057277  mov     ebx, eax
0x180057279  test    eax, eax
0x18005727b  js      short loc_1800572ED
0x18005727d  mov     edi, ebp
0x18005727f  mov     rcx, [rsp+2C8h+lpFileName]; lpFileName
0x180057284  xor     r9d, r9d; lpSecurityAttributes
0x180057287  mov     [rsp+2C8h+hTemplateFile], rbp; hTemplateFile
0x18005728c  xor     r8d, r8d; dwShareMode
0x18005728f  mov     [rsp+2C8h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x180057297  mov     edx, 40000000h; dwDesiredAccess
0x18005729c  mov     [rsp+2C8h+dwCreationDisposition], 2; dwCreationDisposition
0x1800572a4  call    cs:__imp_CreateFileW
0x1800572aa  mov     [rsi+8], rax
0x1800572ae  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800572b2  jnz     short loc_1800572E4
0x1800572b4  call    cs:__imp_GetLastError
0x1800572ba  test    eax, eax
0x1800572bc  jg      short loc_1800572C2
0x1800572be  mov     ebx, eax
0x1800572c0  jmp     short loc_1800572CB
0x1800572c2  movzx   ebx, ax
0x1800572c5  or      ebx, 80070000h
0x1800572cb  cmp     eax, 20h ; ' '
0x1800572ce  jnz     short loc_1800572ED
0x1800572d0  mov     ecx, 0C8h; dwMilliseconds
0x1800572d5  call    cs:__imp_Sleep
0x1800572db  inc     edi
0x1800572dd  cmp     edi, 0Ah
0x1800572e0  jb      short loc_18005727F
0x1800572e2  jmp     short loc_1800572ED
0x1800572e4  mov     ebx, ebp
0x1800572e6  jmp     short loc_1800572ED
0x1800572e8  mov     ebx, 8007000Dh
0x1800572ed  lea     rcx, [rsp+2C8h+var_288]
0x1800572f2  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800572f8  mov     eax, ebx
0x1800572fa  mov     rcx, [rsp+2C8h+var_38]
0x180057302  xor     rcx, rsp; StackCookie
0x180057305  call    __security_check_cookie
0x18005730a  add     rsp, 2A8h
0x180057311  pop     rdi
0x180057312  pop     rsi
0x180057313  pop     rbp
0x180057314  pop     rbx
0x180057315  retn
```
