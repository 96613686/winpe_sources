# container::ObjectManagerProvider::SetupSymlink(Schema::Containers::Definition::ObjectSymlink const &,void *)

- ea: `0x180027438`
- end: `0x180027545`
- name: `?SetupSymlink@ObjectManagerProvider@container@@YAXAEBUObjectSymlink@Definition@Containers@Schema@@PEAX@Z`
- size: `269`
- prototype: `void __fastcall(container::ObjectManagerProvider *__hidden this, const struct Schema::Containers::Definition::ObjectSymlink *, void *)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, installer_update`

## callers

- `0x180026e7c`
- `0x180026f60`

## callees

- `0x180002ad0`
- `0x1800051b0`
- `0x18000d668`
- `0x1800215cc`
- `0x180022eac`
- `0x1800268b8`
- `0x180026c2c`
- `0x180027438`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall container::ObjectManagerProvider::SetupSymlink(
        container::ObjectManagerProvider *this,
        const struct Schema::Containers::Definition::ObjectSymlink *a2,
        void *a3)
{
  int v3; // edi
  __int64 v5; // r8
  __int64 SymbolicLinkTarget; // rax
  __int64 v7; // r9
  container::ObjectManagerProvider *v8; // rbx
  container::ObjectManagerProvider *v9; // rdi
  const struct _tlgProvider_t *v10; // rax
  int v11; // r8d
  int v12; // r9d
  int v13; // [rsp+20h] [rbp-78h]
  container::ObjectManagerProvider *v14; // [rsp+30h] [rbp-68h] BYREF
  container::ObjectManagerProvider *v15; // [rsp+38h] [rbp-60h] BYREF
  _OWORD v16[2]; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v17[32]; // [rsp+60h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v3 = (int)a2;
  v14 = this;
  v16[0] = 0;
  v16[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v16[0]) = 0;
  v5 = *((_QWORD *)this + 6);
  if ( (v5 == 0) == (*((_QWORD *)this + 11) == 0) )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x130,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\ob_provider.cpp",
      (const char *)0x80070057LL,
      v13);
  if ( v5 )
  {
    std::wstring::operator=(v16, (char *)this + 32);
  }
  else
  {
    try
    {
      SymbolicLinkTarget = container::ObjectManager::GetSymbolicLinkTarget((__int64)v17, (const char *)this + 72);
      std::wstring::operator=(v16, SymbolicLinkTarget);
      std::wstring::~wstring(v17);
    }
    catch ( ... )
    {
      v8 = v14;
      v9 = (container::ObjectManagerProvider *)((char *)v14 + 72);
      if ( *((_QWORD *)v14 + 12) > 7u )
        v9 = *(container::ObjectManagerProvider **)v9;
      if ( *((_QWORD *)v14 + 3) > 7u )
        v8 = *(container::ObjectManagerProvider **)v14;
      v10 = ContainerProvider::Provider();
      if ( *(_DWORD *)v10 > 5u )
      {
        v14 = v9;
        v15 = v8;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v10,
          (unsigned int)byte_18003CA63,
          v11,
          v12,
          (__int64)&v15,
          (__int64)&v14);
      }
      goto LABEL_5;
    }
  }
  container::ObjectManager::CreateSymlink(
    this,
    (const WCHAR *)v16,
    v3,
    v7,
    *((_DWORD *)this + 16),
    *((_DWORD *)this + 26));
LABEL_5:
  std::wstring::~wstring(v16);
}

```

## disassembly

```asm
0x180027438  mov     [rsp+arg_8], rbx
0x18002743d  push    rdi
0x18002743e  sub     rsp, 90h
0x180027445  mov     rax, cs:__security_cookie
0x18002744c  xor     rax, rsp
0x18002744f  mov     [rsp+98h+var_18], rax
0x180027457  mov     rdi, rdx
0x18002745a  mov     rbx, rcx
0x18002745d  mov     [rsp+98h+var_68], rcx
0x180027462  xorps   xmm0, xmm0
0x180027465  movups  [rsp+98h+var_58], xmm0
0x18002746a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180027472  movdqu  [rsp+98h+var_48], xmm1
0x180027478  xor     eax, eax
0x18002747a  mov     word ptr [rsp+98h+var_58], ax
0x18002747f  lea     rdx, [rcx+20h]
0x180027483  mov     r8, [rdx+10h]
0x180027487  mov     r10, [rsp+98h]
0x18002748f  cmp     [rcx+58h], rax
0x180027493  setz    cl
0x180027496  test    r8, r8
0x180027499  setz    al
0x18002749c  xor     cl, al
0x18002749e  xor     cl, 1
0x1800274a1  jnz     loc_18002752A
0x1800274a7  test    r8, r8
0x1800274aa  jnz     short loc_1800274D5
0x1800274ac  lea     rdx, [rbx+48h]
0x1800274b0  lea     rcx, [rsp+98h+var_38]
0x1800274b5  call    ?GetSymbolicLinkTarget@ObjectManager@container@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; container::ObjectManager::GetSymbolicLinkTarget(std::wstring const &)
0x1800274ba  mov     rdx, rax
0x1800274bd  lea     rcx, [rsp+98h+var_58]
0x1800274c2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800274c7  lea     rcx, [rsp+98h+var_38]
0x1800274cc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800274d1  jmp     short loc_1800274DF
0x1800274d3  jmp     short loc_1800274FE
0x1800274d5  lea     rcx, [rsp+98h+var_58]
0x1800274da  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800274df  mov     eax, [rbx+68h]
0x1800274e2  mov     [rsp+98h+var_70], eax
0x1800274e6  mov     eax, [rbx+40h]
0x1800274e9  mov     [rsp+98h+var_78], eax
0x1800274ed  mov     r8, rdi
0x1800274f0  lea     rdx, [rsp+98h+var_58]
0x1800274f5  mov     rcx, rbx
0x1800274f8  call    ?CreateSymlink@ObjectManager@container@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEAX_NW4ObjectSymlinkScope@Definition@Containers@Schema@@K@Z; container::ObjectManager::CreateSymlink(std::wstring const &,std::wstring const &,void *,bool,Schema::Containers::Definition::ObjectSymlinkScope,ulong)
0x1800274fd  nop
0x1800274fe  lea     rcx, [rsp+98h+var_58]
0x180027503  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027508  mov     rcx, [rsp+98h+var_18]
0x180027510  xor     rcx, rsp; StackCookie
0x180027513  call    __security_check_cookie
0x180027518  mov     rbx, [rsp+98h+arg_8]
0x180027520  add     rsp, 90h
0x180027527  pop     rdi
0x180027528  retn
0x18002752a  mov     r9d, 80070057h; char *
0x180027530  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\container"...
0x180027537  mov     edx, 130h; void *
0x18002753c  mov     rcx, r10; this
0x18002753f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
