# CLoader::FindObject(IDirectMusicObject *,CObject * *)

- ea: `0x180008710`
- end: `0x18000883a`
- name: `?FindObject@CLoader@@AEAAJPEAUIDirectMusicObject@@PEAPEAVCObject@@@Z`
- size: `298`
- prototype: `__int64 __fastcall(CLoader *__hidden this, struct IDirectMusicObject *, struct CObject **)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x180008af0`
- `0x180009550`
- `0x180009720`

## callees

- `0x1800015d0`
- `0x180001ef0`
- `0x180008710`
- `0x1800089e4`
- `0x180009fdc`
- `0x18000a10c`
- `0x18000a584`
- `0x18000c018`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008799`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008799`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000880b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000880b`

## pseudocode

```c
__int64 __fastcall CLoader::FindObject(CLoader *this, struct IDirectMusicObject *a2, struct CObject **a3)
{
  __int64 v6; // rax
  __int64 result; // rax
  struct _RTL_CRITICAL_SECTION *v8; // rsi
  int Class; // ebx
  unsigned __int64 v10; // rdx
  CClass *v11; // [rsp+30h] [rbp-D0h] BYREF
  struct CObject *v12; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v13[176]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v15[856]; // [rsp+F8h] [rbp-8h] BYREF

  memset_0(v15, 0, 0x350u);
  v6 = *(_QWORD *)a2;
  v14 = 856;
  result = (*(__int64 (__fastcall **)(struct IDirectMusicObject *, __int64 *))(v6 + 24))(a2, &v14);
  if ( (int)result >= 0 )
  {
    CDescriptor::CDescriptor((CDescriptor *)v13);
    CDescriptor::Set((CDescriptor *)v13, (struct _DMUS_OBJECTDESC *)&v14, 0);
    v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 568);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
    v11 = 0;
    v12 = 0;
    Class = CLoader::GetClass(this, (struct CDescriptor *)v13, &v11, 0);
    if ( Class >= 0 )
    {
      Class = CClass::FindObject(v11, (struct CDescriptor *)v13, (struct IDirectMusicObject ***)&v12, 0, a2);
      if ( Class >= 0 )
      {
        if ( *((struct IDirectMusicObject **)v12 + 23) == a2 )
        {
          *a3 = v12;
          Class = 0;
        }
        else
        {
          Class = 1;
        }
      }
    }
    LeaveCriticalSection(v8);
    CDescriptor::~CDescriptor((CDescriptor *)v13, v10);
    return (unsigned int)Class;
  }
  return result;
}

```

## disassembly

```asm
0x180008710  push    rbp
0x180008712  push    rbx
0x180008713  push    rsi
0x180008714  push    rdi
0x180008715  push    r14
0x180008717  lea     rbp, [rsp-360h]
0x18000871f  sub     rsp, 460h
0x180008726  mov     rax, cs:__security_cookie
0x18000872d  xor     rax, rsp
0x180008730  mov     [rbp+380h+var_30], rax
0x180008737  mov     r14, r8
0x18000873a  mov     rdi, rdx
0x18000873d  mov     rbx, rcx
0x180008740  xor     edx, edx; Val
0x180008742  mov     r8d, 350h; Size
0x180008748  lea     rcx, [rbp+380h+var_388]; void *
0x18000874c  call    memset_0
0x180008751  mov     rax, [rdi]
0x180008754  lea     rdx, [rbp+380h+var_390]
0x180008758  mov     rcx, rdi
0x18000875b  mov     [rbp+380h+var_390], 358h
0x180008763  mov     rax, [rax+18h]
0x180008767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000876c  test    eax, eax
0x18000876e  js      loc_18000881D
0x180008774  lea     rcx, [rsp+480h+var_440]; this
0x180008779  call    ??0CDescriptor@@QEAA@XZ; CDescriptor::CDescriptor(void)
0x18000877e  xor     r8d, r8d; struct IStream *
0x180008781  lea     rdx, [rbp+380h+var_390]; struct _DMUS_OBJECTDESC *
0x180008785  lea     rcx, [rsp+480h+var_440]; this
0x18000878a  call    ?Set@CDescriptor@@QEAAXPEAU_DMUS_OBJECTDESC@@PEAUIStream@@@Z; CDescriptor::Set(_DMUS_OBJECTDESC *,IStream *)
0x18000878f  lea     rsi, [rbx+238h]
0x180008796  mov     rcx, rsi; lpCriticalSection
0x180008799  call    cs:__imp_EnterCriticalSection
0x18000879f  xor     r9d, r9d; int
0x1800087a2  mov     [rsp+480h+var_450], 0
0x1800087ab  lea     r8, [rsp+480h+var_450]; struct CClass **
0x1800087b0  mov     [rsp+480h+var_448], 0
0x1800087b9  lea     rdx, [rsp+480h+var_440]; struct CDescriptor *
0x1800087be  mov     rcx, rbx; this
0x1800087c1  call    ?GetClass@CLoader@@AEAAJPEAVCDescriptor@@PEAPEAVCClass@@H@Z; CLoader::GetClass(CDescriptor *,CClass * *,int)
0x1800087c6  mov     ebx, eax
0x1800087c8  test    eax, eax
0x1800087ca  js      short loc_180008808
0x1800087cc  mov     rcx, [rsp+480h+var_450]; this
0x1800087d1  lea     r8, [rsp+480h+var_448]; struct CObject **
0x1800087d6  xor     r9d, r9d; struct CObject *
0x1800087d9  mov     [rsp+480h+var_460], rdi; struct IDirectMusicObject *
0x1800087de  lea     rdx, [rsp+480h+var_440]; struct CDescriptor *
0x1800087e3  call    ?FindObject@CClass@@QEAAJPEAVCDescriptor@@PEAPEAVCObject@@PEAV3@PEAUIDirectMusicObject@@@Z; CClass::FindObject(CDescriptor *,CObject * *,CObject *,IDirectMusicObject *)
0x1800087e8  mov     ebx, eax
0x1800087ea  test    eax, eax
0x1800087ec  js      short loc_180008808
0x1800087ee  mov     rax, [rsp+480h+var_448]
0x1800087f3  cmp     [rax+0B8h], rdi
0x1800087fa  jnz     short loc_180008803
0x1800087fc  mov     [r14], rax
0x1800087ff  xor     ebx, ebx
0x180008801  jmp     short loc_180008808
0x180008803  mov     ebx, 1
0x180008808  mov     rcx, rsi; lpCriticalSection
0x18000880b  call    cs:__imp_LeaveCriticalSection
0x180008811  lea     rcx, [rsp+480h+var_440]; this
0x180008816  call    ??1CDescriptor@@QEAA@XZ; CDescriptor::~CDescriptor(void)
0x18000881b  mov     eax, ebx
0x18000881d  mov     rcx, [rbp+380h+var_30]
0x180008824  xor     rcx, rsp; StackCookie
0x180008827  call    __security_check_cookie
0x18000882c  add     rsp, 460h
0x180008833  pop     r14
0x180008835  pop     rdi
0x180008836  pop     rsi
0x180008837  pop     rbx
0x180008838  pop     rbp
0x180008839  retn
```
