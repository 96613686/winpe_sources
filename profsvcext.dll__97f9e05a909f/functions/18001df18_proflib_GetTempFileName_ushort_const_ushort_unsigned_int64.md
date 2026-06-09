# proflib::_GetTempFileName(ushort const *,ushort *,unsigned __int64)

- ea: `0x18001df18`
- end: `0x18001e0dc`
- name: `?_GetTempFileName@proflib@@YAJPEBGPEAG_K@Z`
- size: `452`
- prototype: `__int64 __fastcall(proflib *this, char *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001da3c`

## callees

- `0x180003b80`
- `0x180008e5c`
- `0x180008ea0`
- `0x18000a520`
- `0x18001de1c`
- `0x18001df18`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001e06b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001e06b`
- `ntdll!NtClose` at `0x18001e07a`
- `ntdll!NtClose` at `0x18001e07a`
- `ntdll!RtlFreeUnicodeString` at `0x18001e01e`
- `ntdll!RtlFreeUnicodeString` at `0x18001e01e`
- `ntdll!RtlStringFromGUID` at `0x18001dfdb`
- `ntdll!RtlStringFromGUID` at `0x18001dfdb`
- `RPCRT4!UuidCreate` at `0x18001dfa1`
- `RPCRT4!UuidCreate` at `0x18001dfa1`

## string_xrefs

- `0x18001e08a`: `Unable to open Tempory File Name: <%ws>.`
- `0x18001e091`: `onecore\ds\security\gina\profile\proflib\dir.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall proflib::_GetTempFileName(proflib *this, char *a2, unsigned __int16 *a3)
{
  signed int v5; // ebx
  unsigned __int16 *v6; // rsi
  unsigned __int64 v7; // rax
  RPC_STATUS v8; // eax
  unsigned int v9; // ecx
  HANDLE FileW; // rax
  int LastErrorMsg; // eax
  struct _UNICODE_STRING GuidString; // [rsp+40h] [rbp-48h] BYREF
  UUID Uuid; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v5 = StringCchCopyW((unsigned __int16 *)a2, (unsigned __int64)a3, (const unsigned __int16 *)this);
  if ( v5 >= 0 )
  {
    *(_QWORD *)&GuidString.Length = 0;
    v5 = StringCchLengthW((const unsigned __int16 *)a2, (unsigned __int64)a3, (unsigned __int64 *)&GuidString.Length);
    if ( v5 >= 0 )
    {
      v6 = (unsigned __int16 *)&a2[2 * *(_QWORD *)&GuidString.Length];
      if ( v6 > (unsigned __int16 *)a2 )
      {
        do
        {
          v7 = (unsigned __int64)(v6 - 1);
          if ( *(v6 - 1) == 92 )
            break;
          --v6;
        }
        while ( v7 > (unsigned __int64)a2 );
      }
      Uuid = 0;
      v8 = UuidCreate(&Uuid);
      if ( v8 != 1824 && v8 )
      {
        if ( v8 > 0 )
          v5 = (unsigned __int16)v8 | 0x80070000;
        else
          v5 = v8;
      }
      if ( v5 >= 0 )
      {
        GuidString = 0;
        if ( RtlStringFromGUID(&Uuid, &GuidString) < 0 )
        {
          return (unsigned int)-2147418113;
        }
        else
        {
          v9 = (_DWORD)a3 - (((char *)v6 - a2) >> 1);
          if ( GuidString.MaximumLength >> 1 > v9 )
            v5 = -2147418113;
          else
            v5 = StringCchCopyW(v6, v9, GuidString.Buffer);
          RtlFreeUnicodeString(&GuidString);
          if ( v5 >= 0 )
          {
            v5 = StringCchCatW((unsigned __int16 *)a2, (unsigned __int64)a3, L".tmp");
            if ( v5 >= 0 )
            {
              FileW = CreateFileW((LPCWSTR)a2, 0x80000000, 0, 0, 1u, 0x80u, 0);
              if ( FileW == (HANDLE)-1LL )
              {
                LastErrorMsg = wil::details::in1diag3::Log_GetLastErrorMsg(
                                 retaddr,
                                 (void *)0xA6,
                                 (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\dir.cpp",
                                 "Unable to open Tempory File Name: <%ws>.",
                                 a2);
                v5 = LastErrorMsg;
                if ( LastErrorMsg > 0 )
                  return (unsigned __int16)LastErrorMsg | 0x80070000;
              }
              else
              {
                NtClose(FileW);
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001df18  mov     [rsp+arg_18], rbx
0x18001df1d  push    rbp
0x18001df1e  push    rsi
0x18001df1f  push    rdi
0x18001df20  sub     rsp, 70h
0x18001df24  mov     rax, cs:__security_cookie
0x18001df2b  xor     rax, rsp
0x18001df2e  mov     [rsp+88h+var_28], rax
0x18001df33  mov     rbp, r8
0x18001df36  mov     rdi, rdx
0x18001df39  mov     r8, rcx; unsigned __int16 *
0x18001df3c  mov     rdx, rbp; unsigned __int64
0x18001df3f  mov     rcx, rdi; unsigned __int16 *
0x18001df42  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001df47  mov     ebx, eax
0x18001df49  test    eax, eax
0x18001df4b  js      loc_18001E0BD
0x18001df51  lea     r8, [rsp+88h+GuidString]; unsigned __int64 *
0x18001df56  mov     qword ptr [rsp+88h+GuidString.Length], 0
0x18001df5f  mov     rdx, rbp; unsigned __int64
0x18001df62  mov     rcx, rdi; unsigned __int16 *
0x18001df65  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001df6a  mov     ebx, eax
0x18001df6c  test    eax, eax
0x18001df6e  js      loc_18001E0BD
0x18001df74  mov     rax, qword ptr [rsp+88h+GuidString.Length]
0x18001df79  lea     rsi, [rdi+rax*2]
0x18001df7d  cmp     rsi, rdi
0x18001df80  jbe     short loc_18001DF94
0x18001df82  lea     rax, [rsi-2]
0x18001df86  cmp     word ptr [rax], 5Ch ; '\'
0x18001df8a  jz      short loc_18001DF94
0x18001df8c  mov     rsi, rax
0x18001df8f  cmp     rax, rdi
0x18001df92  ja      short loc_18001DF82
0x18001df94  xorps   xmm0, xmm0
0x18001df97  lea     rcx, [rsp+88h+Uuid]; Uuid
0x18001df9c  movups  xmmword ptr [rsp+88h+Uuid.Data1], xmm0
0x18001dfa1  call    cs:__imp_UuidCreate
0x18001dfa7  cmp     eax, 720h
0x18001dfac  jz      short loc_18001DFC1
0x18001dfae  test    eax, eax
0x18001dfb0  jz      short loc_18001DFC1
0x18001dfb2  jg      short loc_18001DFB8
0x18001dfb4  mov     ebx, eax
0x18001dfb6  jmp     short loc_18001DFC1
0x18001dfb8  movzx   ebx, ax
0x18001dfbb  or      ebx, 80070000h
0x18001dfc1  test    ebx, ebx
0x18001dfc3  js      loc_18001E0BD
0x18001dfc9  xorps   xmm0, xmm0
0x18001dfcc  lea     rdx, [rsp+88h+GuidString]; GuidString
0x18001dfd1  lea     rcx, [rsp+88h+Uuid]; Guid
0x18001dfd6  movups  xmmword ptr [rsp+88h+GuidString.Length], xmm0
0x18001dfdb  call    cs:__imp_RtlStringFromGUID
0x18001dfe1  test    eax, eax
0x18001dfe3  js      loc_18001E0B8
0x18001dfe9  mov     rax, rsi
0x18001dfec  mov     ecx, ebp
0x18001dfee  sub     rax, rdi
0x18001dff1  sar     rax, 1
0x18001dff4  sub     ecx, eax
0x18001dff6  movzx   eax, [rsp+88h+GuidString.MaximumLength]
0x18001dffb  shr     eax, 1
0x18001dffd  cmp     eax, ecx
0x18001dfff  ja      short loc_18001E014
0x18001e001  mov     r8, [rsp+88h+GuidString.Buffer]; unsigned __int16 *
0x18001e006  mov     edx, ecx; unsigned __int64
0x18001e008  mov     rcx, rsi; unsigned __int16 *
0x18001e00b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e010  mov     ebx, eax
0x18001e012  jmp     short loc_18001E019
0x18001e014  mov     ebx, 8000FFFFh
0x18001e019  lea     rcx, [rsp+88h+GuidString]; UnicodeString
0x18001e01e  call    cs:__imp_RtlFreeUnicodeString
0x18001e024  test    ebx, ebx
0x18001e026  js      loc_18001E0BD
0x18001e02c  lea     r8, aTmp; ".tmp"
0x18001e033  mov     rdx, rbp; unsigned __int64
0x18001e036  mov     rcx, rdi; unsigned __int16 *
0x18001e039  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001e03e  mov     ebx, eax
0x18001e040  test    eax, eax
0x18001e042  js      short loc_18001E0BD
0x18001e044  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x18001e04d  xor     r9d, r9d; lpSecurityAttributes
0x18001e050  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001e058  xor     r8d, r8d; dwShareMode
0x18001e05b  mov     edx, 80000000h; dwDesiredAccess
0x18001e060  mov     [rsp+88h+dwCreationDisposition], 1; dwCreationDisposition
0x18001e068  mov     rcx, rdi; lpFileName
0x18001e06b  call    cs:__imp_CreateFileW
0x18001e071  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001e075  jz      short loc_18001E082
0x18001e077  mov     rcx, rax; Handle
0x18001e07a  call    cs:__imp_NtClose
0x18001e080  jmp     short loc_18001E0BD
0x18001e082  mov     rcx, [rsp+88h]; this
0x18001e08a  lea     r9, aUnableToOpenTe; "Unable to open Tempory File Name: <%ws>"...
0x18001e091  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001e098  mov     qword ptr [rsp+88h+dwCreationDisposition], rdi; char *
0x18001e09d  mov     edx, 0A6h; void *
0x18001e0a2  call    ?Log_GetLastErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBD1ZZ; wil::details::in1diag3::Log_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18001e0a7  mov     ebx, eax
0x18001e0a9  test    eax, eax
0x18001e0ab  jle     short loc_18001E0BD
0x18001e0ad  movzx   ebx, ax
0x18001e0b0  or      ebx, 80070000h
0x18001e0b6  jmp     short loc_18001E0BD
0x18001e0b8  mov     ebx, 8000FFFFh
0x18001e0bd  mov     eax, ebx
0x18001e0bf  mov     rcx, [rsp+88h+var_28]
0x18001e0c4  xor     rcx, rsp; StackCookie
0x18001e0c7  call    __security_check_cookie
0x18001e0cc  mov     rbx, [rsp+88h+arg_18]
0x18001e0d4  add     rsp, 70h
0x18001e0d8  pop     rdi
0x18001e0d9  pop     rsi
0x18001e0da  pop     rbp
0x18001e0db  retn
```
