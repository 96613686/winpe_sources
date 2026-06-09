# CLoader::ScanDirectory(_GUID const &,ushort *,ushort *)

- ea: `0x1800099e0`
- end: `0x180009b15`
- name: `?ScanDirectory@CLoader@@UEAAJAEBU_GUID@@PEAG1@Z`
- size: `309`
- prototype: `__int64 __fastcall(CLoader *__hidden this, const struct _GUID *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800089e4`
- `0x180009844`
- `0x1800099e0`
- `0x180009fdc`
- `0x18000a10c`
- `0x18000bbc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009a96`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009a96`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009ad5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009ad5`

## pseudocode

```c
__int64 __fastcall CLoader::ScanDirectory(
        CLoader *this,
        const struct _GUID *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  struct CClass *v6; // rcx
  struct CClass *v9; // rax
  __int64 *i; // rax
  unsigned int v12; // ebx
  __int128 v13; // xmm0
  unsigned __int16 *v14; // rdx
  unsigned __int64 v15; // rdx
  struct CClass *v16; // [rsp+20h] [rbp-F8h] BYREF
  _BYTE v17[8]; // [rsp+30h] [rbp-E8h] BYREF
  int v18; // [rsp+38h] [rbp-E0h]
  __int128 v19; // [rsp+4Ch] [rbp-CCh]

  v6 = (struct CClass *)*((_QWORD *)this + 3);
  v16 = v6;
  if ( v6 )
  {
    v9 = v6;
    do
    {
      for ( i = (__int64 *)*((_QWORD *)v9 + 25); i; i = (__int64 *)*i )
      {
        *((_DWORD *)i + 48) &= 0xFFFFFFF2;
        *((_DWORD *)i + 48) |= 2u;
      }
      v9 = *(struct CClass **)v6;
      v6 = v9;
    }
    while ( v9 );
    v16 = 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_DirectMusicAllTypes.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_DirectMusicAllTypes.Data4 )
  {
    return 2147746132LL;
  }
  v12 = 0;
  CDescriptor::CDescriptor((CDescriptor *)v17);
  v13 = (__int128)*a2;
  v18 = 2;
  v19 = v13;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
  CLoader::GetClass(this, (struct CDescriptor *)v17, &v16, 1);
  if ( v16 )
  {
    v14 = a3;
    if ( !a3 )
      v14 = (unsigned __int16 *)&qword_180012188;
    v12 = CClass::SearchDirectory(v16, v14);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
  CDescriptor::~CDescriptor((CDescriptor *)v17, v15);
  if ( a4 )
    CLoader::SaveCacheFile((CClass **)this, a4);
  return v12;
}

```

## disassembly

```asm
0x1800099e0  push    rbx
0x1800099e2  push    rbp
0x1800099e3  push    rsi
0x1800099e4  push    rdi
0x1800099e5  push    r14
0x1800099e7  sub     rsp, 0F0h
0x1800099ee  mov     rax, cs:__security_cookie
0x1800099f5  xor     rax, rsp
0x1800099f8  mov     [rsp+118h+var_38], rax
0x180009a00  mov     rsi, rcx
0x180009a03  mov     rbp, r9
0x180009a06  mov     rcx, [rcx+18h]
0x180009a0a  mov     r14, r8
0x180009a0d  mov     [rsp+118h+var_F8], rcx
0x180009a12  mov     rdi, rdx
0x180009a15  test    rcx, rcx
0x180009a18  jz      short loc_180009A4C
0x180009a1a  mov     rax, rcx
0x180009a1d  mov     rax, [rax+0C8h]
0x180009a24  jmp     short loc_180009A37
0x180009a26  and     dword ptr [rax+0C0h], 0FFFFFFF2h
0x180009a2d  or      dword ptr [rax+0C0h], 2
0x180009a34  mov     rax, [rax]
0x180009a37  test    rax, rax
0x180009a3a  jnz     short loc_180009A26
0x180009a3c  mov     rax, [rcx]
0x180009a3f  mov     rcx, rax
0x180009a42  test    rax, rax
0x180009a45  jnz     short loc_180009A1D
0x180009a47  mov     [rsp+118h+var_F8], rax
0x180009a4c  mov     rax, [rdx]
0x180009a4f  cmp     rax, qword ptr cs:GUID_DirectMusicAllTypes.Data1
0x180009a56  jnz     short loc_180009A6F
0x180009a58  mov     rax, [rdx+8]
0x180009a5c  cmp     rax, qword ptr cs:GUID_DirectMusicAllTypes.Data4
0x180009a63  jnz     short loc_180009A6F
0x180009a65  mov     eax, 80040154h
0x180009a6a  jmp     loc_180009AF7
0x180009a6f  lea     rcx, [rsp+118h+var_E8]; this
0x180009a74  xor     ebx, ebx
0x180009a76  call    ??0CDescriptor@@QEAA@XZ; CDescriptor::CDescriptor(void)
0x180009a7b  movups  xmm0, xmmword ptr [rdi]
0x180009a7e  lea     rdi, [rsi+238h]
0x180009a85  mov     [rsp+118h+var_E0], 2
0x180009a8d  mov     rcx, rdi; lpCriticalSection
0x180009a90  movdqu  [rsp+118h+var_CC], xmm0
0x180009a96  call    cs:__imp_EnterCriticalSection
0x180009a9c  lea     r9d, [rbx+1]; int
0x180009aa0  mov     rcx, rsi; this
0x180009aa3  lea     r8, [rsp+118h+var_F8]; struct CClass **
0x180009aa8  lea     rdx, [rsp+118h+var_E8]; struct CDescriptor *
0x180009aad  call    ?GetClass@CLoader@@AEAAJPEAVCDescriptor@@PEAPEAVCClass@@H@Z; CLoader::GetClass(CDescriptor *,CClass * *,int)
0x180009ab2  mov     rcx, [rsp+118h+var_F8]; this
0x180009ab7  test    rcx, rcx
0x180009aba  jz      short loc_180009AD2
0x180009abc  mov     rdx, r14
0x180009abf  test    r14, r14
0x180009ac2  jnz     short loc_180009ACB
0x180009ac4  lea     rdx, qword_180012188; unsigned __int16 *
0x180009acb  call    ?SearchDirectory@CClass@@QEAAJPEAG@Z; CClass::SearchDirectory(ushort *)
0x180009ad0  mov     ebx, eax
0x180009ad2  mov     rcx, rdi; lpCriticalSection
0x180009ad5  call    cs:__imp_LeaveCriticalSection
0x180009adb  lea     rcx, [rsp+118h+var_E8]; this
0x180009ae0  call    ??1CDescriptor@@QEAA@XZ; CDescriptor::~CDescriptor(void)
0x180009ae5  test    rbp, rbp
0x180009ae8  jz      short loc_180009AF5
0x180009aea  mov     rdx, rbp; unsigned __int16 *
0x180009aed  mov     rcx, rsi; this
0x180009af0  call    ?SaveCacheFile@CLoader@@AEAAJPEAG@Z; CLoader::SaveCacheFile(ushort *)
0x180009af5  mov     eax, ebx
0x180009af7  mov     rcx, [rsp+118h+var_38]
0x180009aff  xor     rcx, rsp; StackCookie
0x180009b02  call    __security_check_cookie
0x180009b07  add     rsp, 0F0h
0x180009b0e  pop     r14
0x180009b10  pop     rdi
0x180009b11  pop     rsi
0x180009b12  pop     rbp
0x180009b13  pop     rbx
0x180009b14  retn
```
