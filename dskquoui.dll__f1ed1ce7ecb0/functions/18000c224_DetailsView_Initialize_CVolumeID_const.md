# DetailsView::Initialize(CVolumeID const &)

- ea: `0x18000c224`
- end: `0x18000c456`
- name: `?Initialize@DetailsView@@QEAAHAEBVCVolumeID@@@Z`
- size: `562`
- prototype: `__int64 __fastcall(DetailsView *__hidden this, const struct CVolumeID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800190e4`

## callees

- `0x1800022b4`
- `0x180006ec0`
- `0x180006fb8`
- `0x18000a07c`
- `0x18000c224`
- `0x180019f38`
- `0x18001b878`
- `0x18001b8bc`
- `0x18001b9dc`
- `0x18001ba9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000c246`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000c246`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c410`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c410`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c41e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c41e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
BOOL __fastcall DetailsView::Initialize(DetailsView *this, const struct CVolumeID *a2)
{
  BOOL result; // eax
  int v5; // esi
  HKEY v6; // rdx
  const unsigned __int16 *v7; // r8
  _WORD *v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rcx
  unsigned int v11; // ecx
  _DWORD *v12; // rax
  DetailsView::DataObject *v13; // rax
  HANDLE Thread; // rax
  int v15; // [rsp+30h] [rbp-58h]
  _BYTE v17[48]; // [rsp+40h] [rbp-48h] BYREF

  result = InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 528), 0);
  if ( result )
  {
    v5 = 0;
    v15 = 0;
    *((_DWORD *)this + 168) = 1;
    CString::operator=((char *)this + 248, a2);
    CString::operator=((char *)this + 264, (char *)a2 + 16);
    CString::operator=((char *)this + 280, (char *)a2 + 32);
    try
    {
      *((_BYTE *)this + 296) = *((_BYTE *)a2 + 48);
      if ( (int)DetailsView::CreateVolumeDisplayName(
                  (DetailsView *)((char *)this + 248),
                  (DetailsView *)((char *)this + 304)) < 0 )
        CString::operator=((char *)this + 304, (char *)this + 264);
      RegKey::RegKey((RegKey *)v17, v6, v7);
      if ( RegKey::Open((RegKey *)v17, 0x20019u, 0) >= 0 )
      {
        v8 = (_WORD *)((char *)this + 568);
        if ( (int)RegKey::GetValue((RegKey *)v17, L"Preferences", 3u, (unsigned __int8 *)this + 568, 88) >= 0
          && *v8 == 88
          && *((_WORD *)this + 285) == 3
          && (*((_BYTE *)this + 588) & 0x78u) < 0x40 )
        {
          v9 = 0;
          while ( *(_DWORD *)&v8[2 * v9 + 28] <= 7u )
          {
            v9 = (unsigned int)(v9 + 1);
            if ( (int)v9 >= 8 )
              goto LABEL_16;
          }
        }
      }
      memset_0((char *)this + 572, 0, 0x54u);
      *((_DWORD *)this + 142) = 196696;
      *((_WORD *)this + 294) = *((_WORD *)this + 294) & 0xFF04 | 0x83;
      v10 = 0;
      do
      {
        *((_DWORD *)this + v10 + 156) = v10;
        v10 = (unsigned int)(v10 + 1);
      }
      while ( (unsigned int)v10 < 8 );
LABEL_16:
      v11 = *((unsigned __int16 *)this + 294);
      *((_DWORD *)this + 130) = (v11 >> 3) & 0xF;
      *((_DWORD *)this + 131) = (v11 >> 7) & 1;
      v12 = operator new(0x20u);
      if ( v12 )
      {
        *(_QWORD *)v12 = 0;
        v12[2] = 10;
        *((_QWORD *)v12 + 2) = this;
        *((_QWORD *)v12 + 3) = 0;
      }
      *((_QWORD *)this + 23) = v12;
      v13 = (DetailsView::DataObject *)operator new(0x28u);
      if ( v13 )
        v13 = (DetailsView::DataObject *)DetailsView::DataObject::DataObject(v13, this);
      *((_QWORD *)this + 30) = v13;
      Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)DetailsView::ThreadProc, this, 0, 0);
      if ( Thread )
      {
        CloseHandle(Thread);
        v5 = 1;
        v15 = 1;
      }
      RegKey::~RegKey((RegKey *)v17);
    }
    catch ( CAllocException )
    {
      return v15;
    }
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18000c224  mov     [rsp+arg_10], rbx
0x18000c229  mov     [rsp+arg_18], rsi
0x18000c22e  push    rdi
0x18000c22f  push    r14
0x18000c231  push    r15
0x18000c233  sub     rsp, 70h
0x18000c237  mov     r14, rdx
0x18000c23a  mov     rdi, rcx
0x18000c23d  add     rcx, 210h; lpCriticalSection
0x18000c244  xor     edx, edx; dwSpinCount
0x18000c246  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000c24c  test    eax, eax
0x18000c24e  jz      loc_18000C440
0x18000c254  xor     esi, esi
0x18000c256  mov     [rsp+88h+var_58], esi
0x18000c25a  mov     dword ptr [rdi+2A0h], 1
0x18000c264  lea     rbx, [rdi+0F8h]
0x18000c26b  mov     rdx, r14
0x18000c26e  mov     rcx, rbx
0x18000c271  call    ??4CString@@QEAAAEAV0@AEBV0@@Z; CString::operator=(CString const &)
0x18000c276  lea     rdx, [r14+10h]
0x18000c27a  lea     rcx, [rbx+10h]
0x18000c27e  call    ??4CString@@QEAAAEAV0@AEBV0@@Z; CString::operator=(CString const &)
0x18000c283  lea     rdx, [r14+20h]
0x18000c287  lea     rcx, [rbx+20h]
0x18000c28b  call    ??4CString@@QEAAAEAV0@AEBV0@@Z; CString::operator=(CString const &)
0x18000c290  mov     al, [r14+30h]
0x18000c294  mov     [rbx+30h], al
0x18000c297  lea     r14, [rdi+130h]
0x18000c29e  mov     rdx, r14; struct CString *
0x18000c2a1  mov     rcx, rbx; struct CVolumeID *
0x18000c2a4  call    ?CreateVolumeDisplayName@DetailsView@@SAJAEBVCVolumeID@@PEAVCString@@@Z; DetailsView::CreateVolumeDisplayName(CVolumeID const &,CString *)
0x18000c2a9  test    eax, eax
0x18000c2ab  jns     short loc_18000C2B9
0x18000c2ad  lea     rdx, [rbx+10h]
0x18000c2b1  mov     rcx, r14
0x18000c2b4  call    ??4CString@@QEAAAEAV0@AEBV0@@Z; CString::operator=(CString const &)
0x18000c2b9  lea     rcx, [rsp+88h+var_48]; this
0x18000c2be  call    ??0RegKey@@QEAA@PEAUHKEY__@@PEBG@Z; RegKey::RegKey(HKEY__ *,ushort const *)
0x18000c2c3  nop
0x18000c2c4  xor     r8d, r8d; bool
0x18000c2c7  mov     edx, 20019h; unsigned int
0x18000c2cc  lea     rcx, [rsp+88h+var_48]; this
0x18000c2d1  call    ?Open@RegKey@@QEBAJK_N@Z; RegKey::Open(ulong,bool)
0x18000c2d6  test    eax, eax
0x18000c2d8  js      short loc_18000C333
0x18000c2da  lea     rbx, [rdi+238h]
0x18000c2e1  mov     r14d, 58h ; 'X'
0x18000c2e7  mov     [rsp+88h+dwCreationFlags], r14d; int
0x18000c2ec  mov     r9, rbx; unsigned __int8 *
0x18000c2ef  lea     r15d, [r14-55h]
0x18000c2f3  mov     r8d, r15d; unsigned int
0x18000c2f6  lea     rdx, ValueName; "Preferences"
0x18000c2fd  lea     rcx, [rsp+88h+var_48]; this
0x18000c302  call    ?GetValue@RegKey@@AEBAJPEBGKPEAEH@Z; RegKey::GetValue(ushort const *,ulong,uchar *,int)
0x18000c307  test    eax, eax
0x18000c309  js      short loc_18000C333
0x18000c30b  cmp     [rbx], r14w
0x18000c30f  jnz     short loc_18000C333
0x18000c311  cmp     r15w, [rbx+2]
0x18000c316  jnz     short loc_18000C333
0x18000c318  mov     al, [rbx+14h]
0x18000c31b  and     al, 78h
0x18000c31d  cmp     al, 40h ; '@'
0x18000c31f  jnb     short loc_18000C333
0x18000c321  xor     ecx, ecx
0x18000c323  cmp     dword ptr [rbx+rcx*4+38h], 7
0x18000c328  ja      short loc_18000C333
0x18000c32a  inc     ecx
0x18000c32c  cmp     ecx, 8
0x18000c32f  jl      short loc_18000C323
0x18000c331  jmp     short loc_18000C379
0x18000c333  lea     rcx, [rdi+23Ch]; void *
0x18000c33a  xor     edx, edx; Val
0x18000c33c  lea     r8d, [rdx+54h]; Size
0x18000c340  call    memset_0
0x18000c345  mov     dword ptr [rdi+238h], 30058h
0x18000c34f  movzx   eax, word ptr [rdi+24Ch]
0x18000c356  mov     ecx, 0FF87h
0x18000c35b  and     ax, cx
0x18000c35e  or      ax, 83h
0x18000c362  mov     [rdi+24Ch], ax
0x18000c369  xor     ecx, ecx
0x18000c36b  mov     [rdi+rcx*4+270h], ecx
0x18000c372  inc     ecx
0x18000c374  cmp     ecx, 8
0x18000c377  jb      short loc_18000C36B
0x18000c379  movzx   ecx, word ptr [rdi+24Ch]
0x18000c380  mov     eax, ecx
0x18000c382  shr     eax, 3
0x18000c385  and     eax, 0Fh
0x18000c388  mov     [rdi+208h], eax
0x18000c38e  shr     ecx, 7
0x18000c391  and     ecx, 1
0x18000c394  mov     [rdi+20Ch], ecx
0x18000c39a  mov     ecx, 20h ; ' '; uBytes
0x18000c39f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c3a4  test    rax, rax
0x18000c3a7  jz      short loc_18000C3C3
0x18000c3a9  mov     qword ptr [rax], 0
0x18000c3b0  mov     dword ptr [rax+8], 0Ah
0x18000c3b7  mov     [rax+10h], rdi
0x18000c3bb  mov     qword ptr [rax+18h], 0
0x18000c3c3  mov     [rdi+0B8h], rax
0x18000c3ca  mov     ecx, 28h ; '('; uBytes
0x18000c3cf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c3d4  mov     [rsp+88h+var_50], rax
0x18000c3d9  test    rax, rax
0x18000c3dc  jz      short loc_18000C3EA
0x18000c3de  mov     rdx, rdi; struct DetailsView *
0x18000c3e1  mov     rcx, rax; this
0x18000c3e4  call    ??0DataObject@DetailsView@@QEAA@AEAV1@@Z; DetailsView::DataObject::DataObject(DetailsView &)
0x18000c3e9  nop
0x18000c3ea  mov     [rdi+0F0h], rax
0x18000c3f1  mov     [rsp+88h+lpThreadId], 0; lpThreadId
0x18000c3fa  mov     [rsp+88h+dwCreationFlags], 0; dwCreationFlags
0x18000c402  mov     r9, rdi; lpParameter
0x18000c405  lea     r8, ?ThreadProc@DetailsView@@CAKPEAX@Z; lpStartAddress
0x18000c40c  xor     edx, edx; dwStackSize
0x18000c40e  xor     ecx, ecx; lpThreadAttributes
0x18000c410  call    cs:__imp_CreateThread
0x18000c416  test    rax, rax
0x18000c419  jz      short loc_18000C42D
0x18000c41b  mov     rcx, rax; hObject
0x18000c41e  call    cs:__imp_CloseHandle
0x18000c424  mov     esi, 1
0x18000c429  mov     [rsp+88h+var_58], esi
0x18000c42d  lea     rcx, [rsp+88h+var_48]; this
0x18000c432  call    ??1RegKey@@UEAA@XZ; RegKey::~RegKey(void)
0x18000c437  nop
0x18000c438  jmp     short loc_18000C43E
0x18000c43a  mov     esi, [rsp+88h+var_58]
0x18000c43e  mov     eax, esi
0x18000c440  lea     r11, [rsp+88h+var_18]
0x18000c445  mov     rbx, [r11+30h]
0x18000c449  mov     rsi, [r11+38h]
0x18000c44d  mov     rsp, r11
0x18000c450  pop     r15
0x18000c452  pop     r14
0x18000c454  pop     rdi
0x18000c455  retn
```
