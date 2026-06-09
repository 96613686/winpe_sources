# PushRouter::FindExistingClient(ushort const *)

- ea: `0x180014468`
- end: `0x1800145b4`
- name: `?FindExistingClient@PushRouter@@AEAAPEAVPushClient@@PEBG@Z`
- size: `332`
- prototype: `struct PushClient *__fastcall(PushRouter *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001478c`
- `0x180016110`

## callees

- `0x1800132fc`
- `0x18001420c`
- `0x180014468`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014581`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014581`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800144f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001452d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800144f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001452d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014591`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014591`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800144ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800144ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001459a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001459a`
- `DMCmnUtils!InvStrCmpW` at `0x1800144e9`
- `DMCmnUtils!InvStrCmpW` at `0x18001450d`
- `DMCmnUtils!InvStrCmpW` at `0x180014548`
- `DMCmnUtils!InvStrCmpW` at `0x1800144e9`
- `DMCmnUtils!InvStrCmpW` at `0x18001450d`
- `DMCmnUtils!InvStrCmpW` at `0x180014548`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct PushClient *__fastcall PushRouter::FindExistingClient(PushRouter *this, const unsigned __int16 *a2)
{
  unsigned __int16 *v4; // rsi
  __int64 v5; // rdi
  int v6; // eax
  struct _RTL_CRITICAL_SECTION *v7; // rcx
  struct _RTL_CRITICAL_SECTION *v8; // rbp
  char *v9; // r15
  __int64 v10; // rbx
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF
  unsigned __int16 *v13; // [rsp+78h] [rbp+20h] BYREF

  v4 = 0;
  v13 = 0;
  hKey = 0;
  v5 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\PushRouter\\Registrations\\ByGenericId",
          0,
          0xF003Fu,
          &hKey) )
  {
    v6 = QueryStringValue(hKey, a2, L"GenId", &v13);
    v4 = v13;
    if ( v6 == -2147024882 || !v13 || InvStrCmpW(a2, v13) )
    {
      v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 56);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
      v9 = (char *)this + 24;
      if ( *((_DWORD *)this + 12) )
      {
        v10 = *((_QWORD *)this + 4);
        do
        {
          if ( !InvStrCmpW(*(const unsigned __int16 **)(v10 + 48), a2) )
            break;
          v10 = *(_QWORD *)(v10 + 16);
        }
        while ( v10 );
        if ( v10 )
        {
          CTList<PushClient>::Disconnect(v9, v10);
          (**(void (__fastcall ***)(__int64, __int64))v10)(v10, 1);
        }
      }
      v7 = v8;
    }
    else
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
      if ( *((_DWORD *)this + 12) )
      {
        v5 = *((_QWORD *)this + 4);
        do
        {
          if ( !InvStrCmpW(*(const unsigned __int16 **)(v5 + 48), a2) )
            break;
          v5 = *(_QWORD *)(v5 + 16);
        }
        while ( v5 );
      }
      v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 56);
    }
    LeaveCriticalSection(v7);
  }
  if ( hKey )
    RegCloseKey(hKey);
  LocalFree(v4);
  return (struct PushClient *)v5;
}

```

## disassembly

```asm
0x180014468  mov     r11, rsp
0x18001446b  mov     [r11+8], rbx
0x18001446f  push    rbp
0x180014470  push    rsi
0x180014471  push    rdi
0x180014472  push    r14
0x180014474  push    r15
0x180014476  sub     rsp, 30h
0x18001447a  mov     r14, rdx
0x18001447d  lea     rax, [r11+18h]
0x180014481  mov     rbx, rcx
0x180014484  mov     [r11-38h], rax
0x180014488  xor     esi, esi
0x18001448a  lea     rdx, ?c_szAppRegistrationByGenId@@3QBGB; "Software\\Microsoft\\PushRouter\\Regist"...
0x180014491  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014498  mov     [r11+20h], rsi
0x18001449c  mov     r9d, 0F003Fh; samDesired
0x1800144a2  mov     [r11+18h], rsi
0x1800144a6  xor     r8d, r8d; ulOptions
0x1800144a9  xor     edi, edi
0x1800144ab  call    cs:__imp_RegOpenKeyExW
0x1800144b1  test    eax, eax
0x1800144b3  jnz     loc_180014587
0x1800144b9  mov     rcx, [rsp+58h+hKey]; HKEY
0x1800144be  lea     r9, [rsp+58h+arg_18]; unsigned __int16 **
0x1800144c3  lea     r8, ?c_szGenId@@3QBGB; "GenId"
0x1800144ca  mov     rdx, r14; unsigned __int16 *
0x1800144cd  call    ?QueryStringValue@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; QueryStringValue(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1800144d2  mov     rsi, [rsp+58h+arg_18]
0x1800144d7  cmp     eax, 8007000Eh
0x1800144dc  jz      short loc_180014526
0x1800144de  test    rsi, rsi
0x1800144e1  jz      short loc_180014526
0x1800144e3  mov     rdx, rsi
0x1800144e6  mov     rcx, r14
0x1800144e9  call    cs:__imp_?InvStrCmpW@@YAHPEBG0@Z; InvStrCmpW(ushort const *,ushort const *)
0x1800144ef  test    eax, eax
0x1800144f1  jnz     short loc_180014526
0x1800144f3  lea     rcx, [rbx+38h]; lpCriticalSection
0x1800144f7  call    cs:__imp_EnterCriticalSection
0x1800144fd  cmp     [rbx+30h], edi
0x180014500  jz      short loc_180014520
0x180014502  mov     rdi, [rbx+20h]
0x180014506  mov     rcx, [rdi+30h]
0x18001450a  mov     rdx, r14
0x18001450d  call    cs:__imp_?InvStrCmpW@@YAHPEBG0@Z; InvStrCmpW(ushort const *,ushort const *)
0x180014513  test    eax, eax
0x180014515  jz      short loc_180014520
0x180014517  mov     rdi, [rdi+10h]
0x18001451b  test    rdi, rdi
0x18001451e  jnz     short loc_180014506
0x180014520  lea     rcx, [rbx+38h]
0x180014524  jmp     short loc_180014581
0x180014526  lea     rbp, [rbx+38h]
0x18001452a  mov     rcx, rbp; lpCriticalSection
0x18001452d  call    cs:__imp_EnterCriticalSection
0x180014533  lea     r15, [rbx+18h]
0x180014537  cmp     [r15+18h], edi
0x18001453b  jz      short loc_18001457E
0x18001453d  mov     rbx, [rbx+20h]
0x180014541  mov     rcx, [rbx+30h]
0x180014545  mov     rdx, r14
0x180014548  call    cs:__imp_?InvStrCmpW@@YAHPEBG0@Z; InvStrCmpW(ushort const *,ushort const *)
0x18001454e  test    eax, eax
0x180014550  jz      short loc_18001455B
0x180014552  mov     rbx, [rbx+10h]
0x180014556  test    rbx, rbx
0x180014559  jnz     short loc_180014541
0x18001455b  test    rbx, rbx
0x18001455e  jz      short loc_18001457E
0x180014560  mov     rdx, rbx
0x180014563  mov     rcx, r15
0x180014566  call    ?Disconnect@?$CTList@VPushClient@@@@QEAAPEAVPushClient@@PEAV2@@Z; CTList<PushClient>::Disconnect(PushClient *)
0x18001456b  mov     rax, [rbx]
0x18001456e  mov     edx, 1
0x180014573  mov     rcx, rbx
0x180014576  mov     rax, [rax]
0x180014579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001457e  mov     rcx, rbp; lpCriticalSection
0x180014581  call    cs:__imp_LeaveCriticalSection
0x180014587  mov     rcx, [rsp+58h+hKey]; hKey
0x18001458c  test    rcx, rcx
0x18001458f  jz      short loc_180014597
0x180014591  call    cs:__imp_RegCloseKey
0x180014597  mov     rcx, rsi; hMem
0x18001459a  call    cs:__imp_LocalFree
0x1800145a0  mov     rbx, [rsp+58h+arg_0]
0x1800145a5  mov     rax, rdi
0x1800145a8  add     rsp, 30h
0x1800145ac  pop     r15
0x1800145ae  pop     r14
0x1800145b0  pop     rdi
0x1800145b1  pop     rsi
0x1800145b2  pop     rbp
0x1800145b3  retn
```
