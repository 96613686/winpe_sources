# NgcUtils::IsConsumerUser(ushort const *,bool *)

- ea: `0x1800153ec`
- end: `0x180015586`
- name: `?IsConsumerUser@NgcUtils@@YAJPEBGPEA_N@Z`
- size: `410`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011400`

## callees

- `0x18000113c`
- `0x180003080`
- `0x1800152c8`
- `0x1800153ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015472`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015472`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015468`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800154e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015468`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800154e0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180015447`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180015447`

## pseudocode

```c
__int64 __fastcall NgcUtils::IsConsumerUser(const WCHAR *this, unsigned __int16 *a2, bool *a3)
{
  BOOL v4; // ebx
  enum NgcUserAccountType *Ptr; // r8
  void *v6; // rcx
  signed int LastError; // ebx
  HLOCAL v8; // rcx
  int UserAccountType; // eax
  int v11; // [rsp+30h] [rbp-50h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+40h] [rbp-40h] BYREF
  char v14; // [rsp+50h] [rbp-30h]
  int *v15; // [rsp+60h] [rbp-20h]
  __int64 v16; // [rsp+68h] [rbp-18h]

  if ( !this || !a2 )
    return 2147942487LL;
  *(_BYTE *)a2 = 1;
  v13.Ptr = (ULONGLONG)&hMem;
  hMem = 0;
  *(_QWORD *)&v13.Size = 0;
  v14 = 1;
  v4 = ConvertStringSidToSidW(this, (PSID *)&v13.Size);
  if ( v14 )
  {
    Ptr = (enum NgcUserAccountType *)v13.Ptr;
    v6 = *(void **)v13.Ptr;
    *(_QWORD *)v13.Ptr = *(_QWORD *)&v13.Size;
    if ( v6 )
      LocalFree(v6);
  }
  if ( v4 )
  {
    v11 = 0;
    UserAccountType = NgcUtils::GetUserAccountType((NgcUtils *)hMem, &v11, Ptr);
    LastError = UserAccountType;
    if ( UserAccountType >= 0 )
    {
      *(_BYTE *)a2 = (unsigned int)(v11 - 1) <= 1;
    }
    else if ( (unsigned int)dword_180075000 > 2 )
    {
      v11 = UserAccountType;
      v16 = 4;
      v15 = &v11;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180075000, (unsigned __int8 *)&unk_180068758, 0, 0, 3u, &v13);
    }
  }
  else
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_180075000 > 2 )
    {
      v11 = LastError;
      v15 = &v11;
      v16 = 4;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180075000, (unsigned __int8 *)word_180068782, 0, 0, 3u, &v13);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
  }
  v8 = hMem;
  hMem = 0;
  if ( v8 )
    LocalFree(v8);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800153ec  mov     [rsp-8+arg_10], rbx
0x1800153f1  mov     [rsp-8+arg_18], rdi
0x1800153f6  push    rbp
0x1800153f7  mov     rbp, rsp
0x1800153fa  sub     rsp, 80h
0x180015401  mov     rax, cs:__security_cookie
0x180015408  xor     rax, rsp
0x18001540b  mov     [rbp+var_10], rax
0x18001540f  mov     rdi, rdx
0x180015412  test    rcx, rcx
0x180015415  jz      loc_180015560
0x18001541b  test    rdx, rdx
0x18001541e  jz      loc_180015560
0x180015424  mov     byte ptr [rdx], 1
0x180015427  lea     rax, [rbp+hMem]
0x18001542b  lea     rdx, [rbp+Sid]; Sid
0x18001542f  mov     [rbp+var_40], rax
0x180015433  mov     [rbp+hMem], 0
0x18001543b  mov     [rbp+Sid], 0
0x180015443  mov     [rbp+var_30], 1
0x180015447  call    cs:__imp_ConvertStringSidToSidW
0x18001544d  cmp     [rbp+var_30], 0
0x180015451  mov     ebx, eax
0x180015453  jz      short loc_18001546E
0x180015455  mov     r8, [rbp+var_40]
0x180015459  mov     rdx, [rbp+Sid]
0x18001545d  mov     rcx, [r8]; hMem
0x180015460  mov     [r8], rdx
0x180015463  test    rcx, rcx
0x180015466  jz      short loc_18001546E
0x180015468  call    cs:__imp_LocalFree
0x18001546e  test    ebx, ebx
0x180015470  jnz     short loc_1800154EA
0x180015472  call    cs:__imp_GetLastError
0x180015478  mov     ebx, eax
0x18001547a  mov     eax, cs:dword_180075000
0x180015480  cmp     eax, 2
0x180015483  jbe     short loc_1800154C2
0x180015485  lea     rax, [rbp+var_50]
0x180015489  mov     [rbp+var_50], ebx
0x18001548c  mov     [rbp+var_20], rax
0x180015490  lea     rdx, word_180068782
0x180015497  lea     rax, [rbp+var_40]
0x18001549b  mov     [rbp+var_18], 4
0x1800154a3  mov     [rsp+80h+var_58], rax
0x1800154a8  lea     rcx, dword_180075000
0x1800154af  xor     r9d, r9d
0x1800154b2  mov     [rsp+80h+var_60], 3
0x1800154ba  xor     r8d, r8d
0x1800154bd  call    _tlgWriteTransfer_EventWriteTransfer
0x1800154c2  test    ebx, ebx
0x1800154c4  jle     short loc_1800154CF
0x1800154c6  movzx   ebx, bx
0x1800154c9  or      ebx, 80070000h
0x1800154cf  mov     rcx, [rbp+hMem]; hMem
0x1800154d3  mov     [rbp+hMem], 0
0x1800154db  test    rcx, rcx
0x1800154de  jz      short loc_1800154E6
0x1800154e0  call    cs:__imp_LocalFree
0x1800154e6  mov     eax, ebx
0x1800154e8  jmp     short loc_180015565
0x1800154ea  mov     rcx, [rbp+hMem]; this
0x1800154ee  lea     rdx, [rbp+var_50]; void *
0x1800154f2  mov     [rbp+var_50], 0
0x1800154f9  call    ?GetUserAccountType@NgcUtils@@YAJPEAXPEAW4NgcUserAccountType@@@Z; NgcUtils::GetUserAccountType(void *,NgcUserAccountType *)
0x1800154fe  mov     ebx, eax
0x180015500  test    eax, eax
0x180015502  jns     short loc_18001554E
0x180015504  mov     ecx, cs:dword_180075000
0x18001550a  cmp     ecx, 2
0x18001550d  jbe     short loc_1800154CF
0x18001550f  mov     [rbp+var_50], eax
0x180015512  lea     rdx, unk_180068758
0x180015519  lea     rax, [rbp+var_50]
0x18001551d  mov     [rbp+var_18], 4
0x180015525  mov     [rbp+var_20], rax
0x180015529  lea     rcx, dword_180075000
0x180015530  lea     rax, [rbp+var_40]
0x180015534  xor     r9d, r9d
0x180015537  mov     [rsp+80h+var_58], rax
0x18001553c  xor     r8d, r8d
0x18001553f  mov     [rsp+80h+var_60], 3
0x180015547  call    _tlgWriteTransfer_EventWriteTransfer
0x18001554c  jmp     short loc_1800154CF
0x18001554e  mov     eax, [rbp+var_50]
0x180015551  dec     eax
0x180015553  cmp     eax, 1
0x180015556  setbe   al
0x180015559  mov     [rdi], al
0x18001555b  jmp     loc_1800154CF
0x180015560  mov     eax, 80070057h
0x180015565  mov     rcx, [rbp+var_10]
0x180015569  xor     rcx, rsp; StackCookie
0x18001556c  call    __security_check_cookie
0x180015571  lea     r11, [rsp+80h+var_s0]
0x180015579  mov     rbx, [r11+20h]
0x18001557d  mov     rdi, [r11+28h]
0x180015581  mov     rsp, r11
0x180015584  pop     rbp
0x180015585  retn
```
