# BootTraceSession::Delete(void)

- ea: `0x1800ffc90`
- end: `0x1801000ad`
- name: `?Delete@BootTraceSession@@UEAAJXZ`
- size: `1053`
- prototype: `__int64 __fastcall(BootTraceSession *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800198b0`
- `0x18002b3a0`
- `0x180069150`
- `0x1800ffc90`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180100053`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180100053`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ffd64`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ffd64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ffe37`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ffec9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ffe37`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ffec9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010006f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180100082`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010006f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180100082`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800fff57`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800fff57`

## string_xrefs

- `0x1800ffcc0`: `BootTraceSession::Delete`
- `0x1800ffffb`: `BootTraceSession::Delete`

## pseudocode

```c
__int64 __fastcall BootTraceSession::Delete(BootTraceSession *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rax
  BootTraceSession **v5; // r9
  BootTraceSession **v6; // rax
  LSTATUS v7; // eax
  int v8; // eax
  __int64 v9; // rax
  BootTraceSession *v10; // rcx
  int v11; // eax
  __int64 v12; // rax
  LSTATUS v13; // eax
  int v14; // eax
  __int64 v15; // rax
  int v17; // [rsp+70h] [rbp-90h] BYREF
  BootTraceSession *v18; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR lpSubKey; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v22[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v23[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v24[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v25[64]; // [rsp+220h] [rbp+120h] BYREF

  v17 = *((_DWORD *)this + 14);
  lpSubKey = 0;
  hKey = 0;
  phkResult = 0;
  v18 = this;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_METHOD, 3, "BootTraceSession::Delete", 25, &v18, 8, &v17, 4);
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v2 = (*(__int64 (__fastcall **)(BootTraceSession *, LPCWSTR *))(*(_QWORD *)this + 160LL))(this, &lpSubKey);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\WMI\\AutoLogger", 0, 0x2001Fu, &hKey);
    v8 = PlaiHResultFromWin32(v7);
    v3 = v8;
    if ( v8 >= 0 )
    {
      RegOpenKeyExW(hKey, lpSubKey, 0, 0x2001Fu, &phkResult);
      v11 = BootTraceSession::DeleteProviders(v10, phkResult);
      v3 = v11;
      if ( v11 >= 0 )
      {
        v13 = RegDeleteKeyW(hKey, lpSubKey);
        if ( v13 == 2 )
        {
          v3 = -2144337918;
          v14 = -2144337918;
        }
        else
        {
          v14 = PlaiHResultFromWin32(v13);
          v3 = v14;
          if ( v14 >= 0 )
            goto LABEL_39;
        }
        LODWORD(v18) = 0;
        v17 = v14;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_39;
        }
        PlaiWhoAmI(v25, 0x4000000000000800uLL);
        v15 = -1;
        do
          ++v15;
        while ( v25[v15] );
      }
      else
      {
        LODWORD(v18) = 0;
        v17 = v11;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_39;
        }
        PlaiWhoAmI(v24, 0x4000000000000800uLL);
        v12 = -1;
        do
          ++v12;
        while ( v24[v12] );
      }
    }
    else
    {
      LODWORD(v18) = 0;
      v17 = v8;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_39;
      }
      PlaiWhoAmI(v23, 0x4000000000000800uLL);
      v9 = -1;
      do
        ++v9;
      while ( v23[v9] );
    }
    v5 = (BootTraceSession **)&v17;
    v6 = &v18;
LABEL_38:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v5, 4, byte_180147320, 1, v6, 4);
    goto LABEL_39;
  }
  v17 = 0;
  LODWORD(v18) = v2;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v22, 0x4000000000000800uLL);
    v4 = -1;
    do
      ++v4;
    while ( v22[v4] );
    v5 = &v18;
    v6 = (BootTraceSession **)&v17;
    goto LABEL_38;
  }
LABEL_39:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  PlaiFreeString((BSTR)lpSubKey);
  lpSubKey = 0;
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return v3;
}

```

## disassembly

```asm
0x1800ffc90  push    rbp
0x1800ffc92  push    rbx
0x1800ffc93  push    rsi
0x1800ffc94  push    rdi
0x1800ffc95  push    r12
0x1800ffc97  push    r13
0x1800ffc99  push    r14
0x1800ffc9b  push    r15
0x1800ffc9d  lea     rbp, [rsp-1B8h]
0x1800ffca5  sub     rsp, 2B8h
0x1800ffcac  mov     rax, cs:__security_cookie
0x1800ffcb3  xor     rax, rsp
0x1800ffcb6  mov     [rbp+1F0h+var_50], rax
0x1800ffcbd  mov     eax, [rcx+38h]
0x1800ffcc0  lea     r14, aBoottracesessi_4; "BootTraceSession::Delete"
0x1800ffcc7  xor     esi, esi
0x1800ffcc9  mov     [rsp+2F0h+var_280], eax
0x1800ffccd  cmp     dword ptr cs:xmmword_180169738, esi
0x1800ffcd3  lea     r13, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800ffcda  mov     rdi, rcx
0x1800ffcdd  mov     [rbp+1F0h+lpSubKey], rsi
0x1800ffce1  mov     [rbp+1F0h+hKey], rsi
0x1800ffce5  lea     r15d, [rsi+4]
0x1800ffce9  mov     [rbp+1F0h+var_260], rsi
0x1800ffced  lea     r12d, [rsi+19h]
0x1800ffcf1  mov     [rsp+2F0h+var_278], rcx
0x1800ffcf6  jz      short loc_1800FFD5B
0x1800ffcf8  mov     rdx, 4000000000000400h
0x1800ffd02  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ffd09  jz      short loc_1800FFD5B
0x1800ffd0b  mov     rax, cs:qword_180169748
0x1800ffd12  and     rax, rdx
0x1800ffd15  cmp     cs:qword_180169748, rax
0x1800ffd1c  jnz     short loc_1800FFD5B
0x1800ffd1e  mov     [rsp+2F0h+var_2B0], r15
0x1800ffd23  lea     rax, [rsp+2F0h+var_280]
0x1800ffd28  mov     [rsp+2F0h+var_2B8], rax
0x1800ffd2d  lea     r8d, [rsi+3]
0x1800ffd31  lea     rax, [rsp+2F0h+var_278]
0x1800ffd36  mov     [rsp+2F0h+var_2C0], 8
0x1800ffd3f  mov     [rsp+2F0h+var_2C8], rax
0x1800ffd44  lea     rdx, PLA_EVENT_METHOD
0x1800ffd4b  mov     r9, r14
0x1800ffd4e  mov     [rsp+2F0h+phkResult], r12
0x1800ffd53  mov     rcx, r13
0x1800ffd56  call    EventingWriteEvent
0x1800ffd5b  cmp     [rdi+8], esi
0x1800ffd5e  jz      short loc_1800FFD6A
0x1800ffd60  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800ffd64  call    cs:__imp_EnterCriticalSection
0x1800ffd6a  mov     rax, [rdi]
0x1800ffd6d  lea     rdx, [rbp+1F0h+lpSubKey]
0x1800ffd71  mov     rcx, rdi
0x1800ffd74  mov     rax, [rax+0A0h]
0x1800ffd7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffd80  mov     ebx, eax
0x1800ffd82  test    eax, eax
0x1800ffd84  jns     loc_1800FFE14
0x1800ffd8a  cmp     dword ptr cs:xmmword_180169738, esi
0x1800ffd90  mov     [rsp+2F0h+var_280], esi
0x1800ffd94  mov     dword ptr [rsp+2F0h+var_278], eax
0x1800ffd98  jz      loc_18010004A
0x1800ffd9e  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ffda8  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ffdaf  jz      loc_18010004A
0x1800ffdb5  mov     rax, cs:qword_180169748
0x1800ffdbc  and     rax, rdx
0x1800ffdbf  cmp     cs:qword_180169748, rax
0x1800ffdc6  jnz     loc_18010004A
0x1800ffdcc  lea     rcx, [rbp+1F0h+var_250]; unsigned __int16 *
0x1800ffdd0  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ffdd5  lea     rcx, [rbp+1F0h+var_250]
0x1800ffdd9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ffddd  inc     rax
0x1800ffde0  cmp     [rcx+rax*2], si
0x1800ffde4  jnz     short loc_1800FFDDD
0x1800ffde6  lea     ecx, [rax+rax]
0x1800ffde9  lea     rax, [rbp+1F0h+var_250]
0x1800ffded  add     rcx, 2
0x1800ffdf1  mov     [rsp+2F0h+var_290], rcx
0x1800ffdf6  lea     r9, [rsp+2F0h+var_278]
0x1800ffdfb  mov     [rsp+2F0h+var_298], rax
0x1800ffe00  lea     rax, [rsp+2F0h+var_280]
0x1800ffe05  mov     [rsp+2F0h+var_2A0], r12
0x1800ffe0a  mov     [rsp+2F0h+var_2A8], r14
0x1800ffe0f  jmp     loc_180100011
0x1800ffe14  lea     rax, [rbp+1F0h+hKey]
0x1800ffe18  mov     r14d, 2001Fh
0x1800ffe1e  mov     r9d, r14d; samDesired
0x1800ffe21  mov     [rsp+2F0h+phkResult], rax; phkResult
0x1800ffe26  xor     r8d, r8d; ulOptions
0x1800ffe29  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\WMI"...
0x1800ffe30  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ffe37  call    cs:__imp_RegOpenKeyExW
0x1800ffe3d  mov     ecx, eax; unsigned int
0x1800ffe3f  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800ffe44  mov     ebx, eax
0x1800ffe46  test    eax, eax
0x1800ffe48  jns     short loc_1800FFEB2
0x1800ffe4a  cmp     dword ptr cs:xmmword_180169738, esi
0x1800ffe50  mov     dword ptr [rsp+2F0h+var_278], esi
0x1800ffe54  mov     [rsp+2F0h+var_280], eax
0x1800ffe58  jz      loc_18010004A
0x1800ffe5e  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ffe68  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ffe6f  jz      loc_18010004A
0x1800ffe75  mov     rax, cs:qword_180169748
0x1800ffe7c  and     rax, rdx
0x1800ffe7f  cmp     cs:qword_180169748, rax
0x1800ffe86  jnz     loc_18010004A
0x1800ffe8c  lea     rcx, [rbp+1F0h+var_1D0]; unsigned __int16 *
0x1800ffe90  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ffe95  lea     rcx, [rbp+1F0h+var_1D0]
0x1800ffe99  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ffe9d  inc     rax
0x1800ffea0  cmp     [rcx+rax*2], si
0x1800ffea4  jnz     short loc_1800FFE9D
0x1800ffea6  lea     ecx, [rax+rax]
0x1800ffea9  lea     rax, [rbp+1F0h+var_1D0]
0x1800ffead  jmp     loc_1800FFFE8
0x1800ffeb2  mov     rdx, [rbp+1F0h+lpSubKey]; lpSubKey
0x1800ffeb6  lea     rax, [rbp+1F0h+var_260]
0x1800ffeba  mov     rcx, [rbp+1F0h+hKey]; hKey
0x1800ffebe  mov     r9d, r14d; samDesired
0x1800ffec1  xor     r8d, r8d; ulOptions
0x1800ffec4  mov     [rsp+2F0h+phkResult], rax; phkResult
0x1800ffec9  call    cs:__imp_RegOpenKeyExW
0x1800ffecf  mov     rdx, [rbp+1F0h+var_260]; HKEY
0x1800ffed3  call    ?DeleteProviders@BootTraceSession@@AEAAJPEAUHKEY__@@@Z; BootTraceSession::DeleteProviders(HKEY__ *)
0x1800ffed8  mov     ebx, eax
0x1800ffeda  test    eax, eax
0x1800ffedc  jns     short loc_1800FFF4F
0x1800ffede  cmp     dword ptr cs:xmmword_180169738, esi
0x1800ffee4  mov     dword ptr [rsp+2F0h+var_278], esi
0x1800ffee8  mov     [rsp+2F0h+var_280], eax
0x1800ffeec  jz      loc_18010004A
0x1800ffef2  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ffefc  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800fff03  jz      loc_18010004A
0x1800fff09  mov     rax, cs:qword_180169748
0x1800fff10  and     rax, rdx
0x1800fff13  cmp     cs:qword_180169748, rax
0x1800fff1a  jnz     loc_18010004A
0x1800fff20  lea     rcx, [rbp+1F0h+var_150]; unsigned __int16 *
0x1800fff27  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800fff2c  lea     rcx, [rbp+1F0h+var_150]
0x1800fff33  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800fff37  inc     rax
0x1800fff3a  cmp     [rcx+rax*2], si
0x1800fff3e  jnz     short loc_1800FFF37
0x1800fff40  lea     ecx, [rax+rax]
0x1800fff43  lea     rax, [rbp+1F0h+var_150]
0x1800fff4a  jmp     loc_1800FFFE8
0x1800fff4f  mov     rdx, [rbp+1F0h+lpSubKey]; lpSubKey
0x1800fff53  mov     rcx, [rbp+1F0h+hKey]; hKey
0x1800fff57  call    cs:__imp_RegDeleteKeyW
0x1800fff5d  cmp     eax, 2
0x1800fff60  jz      short loc_1800FFF75
0x1800fff62  mov     ecx, eax; unsigned int
0x1800fff64  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800fff69  mov     ebx, eax
0x1800fff6b  test    eax, eax
0x1800fff6d  jns     loc_18010004A
0x1800fff73  jmp     short loc_1800FFF7C
0x1800fff75  mov     ebx, 80300002h
0x1800fff7a  mov     eax, ebx
0x1800fff7c  cmp     dword ptr cs:xmmword_180169738, esi
0x1800fff82  mov     dword ptr [rsp+2F0h+var_278], esi
0x1800fff86  mov     [rsp+2F0h+var_280], eax
0x1800fff8a  jz      loc_18010004A
0x1800fff90  mov     rdx, 4000000000000800h; unsigned __int64
0x1800fff9a  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800fffa1  jz      loc_18010004A
0x1800fffa7  mov     rax, cs:qword_180169748
0x1800fffae  and     rax, rdx
0x1800fffb1  cmp     cs:qword_180169748, rax
0x1800fffb8  jnz     loc_18010004A
0x1800fffbe  lea     rcx, [rbp+1F0h+var_D0]; unsigned __int16 *
0x1800fffc5  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800fffca  lea     rcx, [rbp+1F0h+var_D0]
0x1800fffd1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800fffd5  inc     rax
0x1800fffd8  cmp     [rcx+rax*2], si
0x1800fffdc  jnz     short loc_1800FFFD5
0x1800fffde  lea     ecx, [rax+rax]
0x1800fffe1  lea     rax, [rbp+1F0h+var_D0]
0x1800fffe8  add     rcx, 2
0x1800fffec  lea     r9, [rsp+2F0h+var_280]
0x1800ffff1  mov     [rsp+2F0h+var_290], rcx
0x1800ffff6  mov     [rsp+2F0h+var_298], rax
0x1800ffffb  lea     rax, aBoottracesessi_4; "BootTraceSession::Delete"
0x180100002  mov     [rsp+2F0h+var_2A0], r12
0x180100007  mov     [rsp+2F0h+var_2A8], rax
0x18010000c  lea     rax, [rsp+2F0h+var_278]
0x180100011  mov     [rsp+2F0h+var_2B0], r15
0x180100016  lea     rdx, PLA_EVENT_ERROR
0x18010001d  mov     [rsp+2F0h+var_2B8], rax
0x180100022  mov     r8d, 5
0x180100028  lea     rax, byte_180147320
0x18010002f  mov     [rsp+2F0h+var_2C0], 1
0x180100038  mov     [rsp+2F0h+var_2C8], rax
0x18010003d  mov     rcx, r13
0x180100040  mov     [rsp+2F0h+phkResult], r15
0x180100045  call    EventingWriteEvent
0x18010004a  cmp     [rdi+8], esi
0x18010004d  jz      short loc_180100059
0x18010004f  lea     rcx, [rdi+10h]; lpCriticalSection
0x180100053  call    cs:__imp_LeaveCriticalSection
0x180100059  mov     rcx, [rbp+1F0h+lpSubKey]; bstrString
0x18010005d  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x180100062  mov     rcx, [rbp+1F0h+hKey]; hKey
0x180100066  mov     [rbp+1F0h+lpSubKey], rsi
0x18010006a  test    rcx, rcx
0x18010006d  jz      short loc_180100079
0x18010006f  call    cs:__imp_RegCloseKey
0x180100075  mov     [rbp+1F0h+hKey], rsi
0x180100079  mov     rcx, [rbp+1F0h+var_260]; hKey
0x18010007d  test    rcx, rcx
0x180100080  jz      short loc_180100088
0x180100082  call    cs:__imp_RegCloseKey
0x180100088  mov     eax, ebx
0x18010008a  mov     rcx, [rbp+1F0h+var_50]
0x180100091  xor     rcx, rsp; StackCookie
0x180100094  call    __security_check_cookie
0x180100099  add     rsp, 2B8h
0x1801000a0  pop     r15
0x1801000a2  pop     r14
0x1801000a4  pop     r13
0x1801000a6  pop     r12
0x1801000a8  pop     rdi
0x1801000a9  pop     rsi
0x1801000aa  pop     rbx
0x1801000ab  pop     rbp
0x1801000ac  retn
```
