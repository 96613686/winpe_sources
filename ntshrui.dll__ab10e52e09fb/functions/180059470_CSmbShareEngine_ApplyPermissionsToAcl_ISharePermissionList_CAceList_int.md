# CSmbShareEngine::_ApplyPermissionsToAcl(ISharePermissionList *,CAceList *,int)

- ea: `0x180059470`
- end: `0x1800595e0`
- name: `?_ApplyPermissionsToAcl@CSmbShareEngine@@AEAAJPEAUISharePermissionList@@PEAVCAceList@@H@Z`
- size: `368`
- prototype: `int(CSmbShareEngine *__hidden this, struct ISharePermissionList *, struct CAceList *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180059a80`
- `0x18005cba4`

## callees

- `0x18000f840`
- `0x18002ad00`
- `0x1800564bc`
- `0x180059470`
- `0x18005e1c8`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005957a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005957a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005958b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005958b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180059526`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180059526`

## pseudocode

```c
__int64 __fastcall CSmbShareEngine::_ApplyPermissionsToAcl(
        CSmbShareEngine *this,
        struct ISharePermissionList *a2,
        struct CAceList *a3,
        enum SHARE_ROLE a4)
{
  __int64 v4; // rax
  unsigned int v8; // edi
  int v9; // ebx
  __int64 v10; // rax
  unsigned int ItemAccessMaskForRole; // eax
  int v12; // r8d
  int v13; // ebx
  LPCWSTR StringSid; // [rsp+30h] [rbp-10h] BYREF
  PSID Sid; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v17; // [rsp+78h] [rbp+38h] BYREF
  enum SHARE_ROLE v18; // [rsp+88h] [rbp+48h] BYREF

  v18 = a4;
  v4 = *(_QWORD *)a2;
  v17 = 0;
  v8 = 0;
  v9 = (*(__int64 (__fastcall **)(struct ISharePermissionList *, unsigned int *))(v4 + 32))(a2, &v17);
  if ( v9 < 0 )
  {
LABEL_13:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        WPP_055da27402593bc4c79a5720b75a8198_Traceguids,
        (unsigned int)v9);
  }
  else
  {
    while ( v8 < v17 )
    {
      v10 = *(_QWORD *)a2;
      StringSid = 0;
      v18 = SHARE_ROLE_READER;
      v9 = (*(__int64 (__fastcall **)(struct ISharePermissionList *, _QWORD, LPCWSTR *, enum SHARE_ROLE *))(v10 + 40))(
             a2,
             v8,
             &StringSid,
             &v18);
      if ( v9 >= 0 )
      {
        if ( !(*(unsigned int (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 1) + 8LL))(
                (char *)this + 8,
                (unsigned int)v18) )
        {
          Sid = 0;
          if ( ConvertStringSidToSidW(StringSid, &Sid) )
          {
            ItemAccessMaskForRole = GetItemAccessMaskForRole(v18);
            v13 = ItemAccessMaskForRole;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, v12, (_DWORD)StringSid, ItemAccessMaskForRole);
            v9 = CAceList::SetExplicitAllowAce(a3, Sid, v13, 3);
            LocalFree(Sid);
          }
          else
          {
            v9 = -2147024882;
          }
        }
        CoTaskMemFree((LPVOID)StringSid);
      }
      ++v8;
      if ( v9 < 0 )
        goto LABEL_13;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180059470  mov     [rsp-28h+arg_0], rbx
0x180059475  mov     [rsp-28h+arg_10], rsi
0x18005947a  mov     [rsp-28h+arg_18], r9d
0x18005947f  push    rbp
0x180059480  push    rdi
0x180059481  push    r13
0x180059483  push    r14
0x180059485  push    r15
0x180059487  mov     rbp, rsp
0x18005948a  sub     rsp, 40h
0x18005948e  mov     rax, [rdx]
0x180059491  mov     rsi, rdx
0x180059494  mov     r15, rcx
0x180059497  mov     [rbp+arg_8], 0
0x18005949e  lea     rdx, [rbp+arg_8]
0x1800594a2  mov     rcx, rsi
0x1800594a5  mov     r14, r8
0x1800594a8  mov     rax, [rax+20h]
0x1800594ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800594b1  xor     edi, edi
0x1800594b3  lea     r13, WPP_GLOBAL_Control
0x1800594ba  mov     ebx, eax
0x1800594bc  test    eax, eax
0x1800594be  js      loc_18005959B
0x1800594c4  cmp     edi, [rbp+arg_8]
0x1800594c7  jnb     loc_1800595C5
0x1800594cd  mov     rax, [rsi]
0x1800594d0  lea     r9, [rbp+arg_18]
0x1800594d4  lea     r8, [rbp+StringSid]
0x1800594d8  mov     [rbp+StringSid], 0
0x1800594e0  mov     edx, edi
0x1800594e2  mov     [rbp+arg_18], 0
0x1800594e9  mov     rcx, rsi
0x1800594ec  mov     rax, [rax+28h]
0x1800594f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800594f5  mov     ebx, eax
0x1800594f7  test    eax, eax
0x1800594f9  js      loc_180059591
0x1800594ff  mov     edx, [rbp+arg_18]
0x180059502  lea     rcx, [r15+8]
0x180059506  mov     rax, [rcx]
0x180059509  mov     rax, [rax+8]
0x18005950d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059512  test    eax, eax
0x180059514  jnz     short loc_180059587
0x180059516  mov     rcx, [rbp+StringSid]; StringSid
0x18005951a  lea     rdx, [rbp+Sid]; Sid
0x18005951e  mov     [rbp+Sid], 0
0x180059526  call    cs:__imp_ConvertStringSidToSidW
0x18005952c  test    eax, eax
0x18005952e  jz      short loc_180059582
0x180059530  mov     ecx, [rbp+arg_18]; enum SHARE_ROLE
0x180059533  call    ?GetItemAccessMaskForRole@@YAKW4SHARE_ROLE@@@Z; GetItemAccessMaskForRole(SHARE_ROLE)
0x180059538  mov     ebx, eax
0x18005953a  mov     rcx, cs:WPP_GLOBAL_Control
0x180059541  cmp     rcx, r13
0x180059544  jz      short loc_180059562
0x180059546  test    byte ptr [rcx+1Ch], 8
0x18005954a  jz      short loc_180059562
0x18005954c  mov     r9, [rbp+StringSid]
0x180059550  mov     edx, 41h ; 'A'
0x180059555  mov     rcx, [rcx+10h]
0x180059559  mov     [rsp+40h+var_20], eax
0x18005955d  call    WPP_SF_Sd
0x180059562  mov     rdx, [rbp+Sid]; void *
0x180059566  mov     r9b, 3; unsigned __int8
0x180059569  mov     r8d, ebx; unsigned int
0x18005956c  mov     rcx, r14; this
0x18005956f  call    ?SetExplicitAllowAce@CAceList@@QEAAJPEAXKE@Z; CAceList::SetExplicitAllowAce(void *,ulong,uchar)
0x180059574  mov     rcx, [rbp+Sid]; hMem
0x180059578  mov     ebx, eax
0x18005957a  call    cs:__imp_LocalFree
0x180059580  jmp     short loc_180059587
0x180059582  mov     ebx, 8007000Eh
0x180059587  mov     rcx, [rbp+StringSid]; pv
0x18005958b  call    cs:__imp_CoTaskMemFree
0x180059591  inc     edi
0x180059593  test    ebx, ebx
0x180059595  jns     loc_1800594C4
0x18005959b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800595a2  cmp     rcx, r13
0x1800595a5  jz      short loc_1800595C5
0x1800595a7  test    byte ptr [rcx+1Ch], 2
0x1800595ab  jz      short loc_1800595C5
0x1800595ad  mov     rcx, [rcx+10h]
0x1800595b1  lea     r8, WPP_055da27402593bc4c79a5720b75a8198_Traceguids
0x1800595b8  mov     edx, 42h ; 'B'
0x1800595bd  mov     r9d, ebx
0x1800595c0  call    WPP_SF_d
0x1800595c5  lea     r11, [rsp+40h+var_s0]
0x1800595ca  mov     eax, ebx
0x1800595cc  mov     rbx, [r11+30h]
0x1800595d0  mov     rsi, [r11+40h]
0x1800595d4  mov     rsp, r11
0x1800595d7  pop     r15
0x1800595d9  pop     r14
0x1800595db  pop     r13
0x1800595dd  pop     rdi
0x1800595de  pop     rbp
0x1800595df  retn
```
