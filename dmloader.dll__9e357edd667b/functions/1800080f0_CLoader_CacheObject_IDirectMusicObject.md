# CLoader::CacheObject(IDirectMusicObject *)

- ea: `0x1800080f0`
- end: `0x180008278`
- name: `?CacheObject@CLoader@@UEAAJPEAUIDirectMusicObject@@@Z`
- size: `392`
- prototype: `__int64 __fastcall(CLoader *__hidden this, struct IDirectMusicObject *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800015d0`
- `0x180001ef0`
- `0x1800080f0`
- `0x1800089e4`
- `0x180009fdc`
- `0x18000a10c`
- `0x18000a584`
- `0x18000c018`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800081af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800081af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008232`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008232`

## pseudocode

```c
__int64 __fastcall CLoader::CacheObject(CLoader *this, struct IDirectMusicObject *a2)
{
  _QWORD *v4; // rax
  __int64 (__fastcall *v5)(struct IDirectMusicObject *, int *); // rax
  int Class; // ebx
  struct CObject *v7; // rsi
  int Object; // eax
  struct IDirectMusicObject *v9; // rcx
  unsigned __int64 v10; // rdx
  CClass *v12; // [rsp+30h] [rbp-D0h] BYREF
  struct CObject *v13; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v14[176]; // [rsp+40h] [rbp-C0h] BYREF
  int v15; // [rsp+F0h] [rbp-10h] BYREF
  _DWORD v16[215]; // [rsp+F4h] [rbp-Ch] BYREF

  memset_0(v16, 0, 0x354u);
  v15 = 856;
  if ( a2 )
  {
    v4 = *(_QWORD **)a2;
    if ( *(_QWORD *)a2 )
    {
      if ( *v4 )
      {
        v5 = (__int64 (__fastcall *)(struct IDirectMusicObject *, int *))v4[3];
        v16[0] = 0;
        Class = v5(a2, &v15);
        if ( Class < 0 )
          return (unsigned int)Class;
        CDescriptor::CDescriptor((CDescriptor *)v14);
        CDescriptor::Set((CDescriptor *)v14, (struct _DMUS_OBJECTDESC *)&v15, 0);
        v12 = 0;
        v7 = 0;
        v13 = 0;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
        Class = CLoader::GetClass(this, (struct CDescriptor *)v14, &v12, 0);
        if ( Class >= 0 )
        {
          Object = CClass::FindObject(v12, (struct CDescriptor *)v14, &v13, 0, 0);
          v7 = v13;
          Class = Object;
        }
        if ( Class >= 0 )
        {
          v9 = (struct IDirectMusicObject *)*((_QWORD *)v7 + 23);
          if ( v9 )
          {
            if ( v9 == a2 )
            {
              Class = 1;
              goto LABEL_12;
            }
            (*(void (__fastcall **)(struct IDirectMusicObject *))(*(_QWORD *)v9 + 16LL))(v9);
          }
          *((_QWORD *)v7 + 23) = a2;
          *((_DWORD *)v7 + 4) |= 0x200u;
          (*(void (__fastcall **)(struct IDirectMusicObject *))(*(_QWORD *)a2 + 8LL))(a2);
        }
LABEL_12:
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
        CDescriptor::~CDescriptor((CDescriptor *)v14, v10);
        return (unsigned int)Class;
      }
    }
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x1800080f0  mov     [rsp-8+arg_10], rbx
0x1800080f5  push    rbp
0x1800080f6  push    rsi
0x1800080f7  push    rdi
0x1800080f8  push    r14
0x1800080fa  push    r15
0x1800080fc  lea     rbp, [rsp-360h]
0x180008104  sub     rsp, 460h
0x18000810b  mov     rax, cs:__security_cookie
0x180008112  xor     rax, rsp
0x180008115  mov     [rbp+380h+var_30], rax
0x18000811c  mov     rdi, rdx
0x18000811f  mov     r15, rcx
0x180008122  xor     edx, edx; Val
0x180008124  lea     rcx, [rbp+380h+var_38C]; void *
0x180008128  mov     r8d, 354h; Size
0x18000812e  call    memset_0
0x180008133  mov     [rbp+380h+var_390], 358h
0x18000813a  test    rdi, rdi
0x18000813d  jz      loc_18000824D
0x180008143  mov     rax, [rdi]
0x180008146  test    rax, rax
0x180008149  jz      loc_18000824D
0x18000814f  cmp     qword ptr [rax], 0
0x180008153  jz      loc_18000824D
0x180008159  mov     rax, [rax+18h]
0x18000815d  lea     rdx, [rbp+380h+var_390]
0x180008161  mov     rcx, rdi
0x180008164  mov     [rbp+380h+var_38C], 0
0x18000816b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008170  mov     ebx, eax
0x180008172  test    eax, eax
0x180008174  js      loc_180008242
0x18000817a  lea     rcx, [rsp+480h+var_440]; this
0x18000817f  call    ??0CDescriptor@@QEAA@XZ; CDescriptor::CDescriptor(void)
0x180008184  xor     r8d, r8d; struct IStream *
0x180008187  lea     rdx, [rbp+380h+var_390]; struct _DMUS_OBJECTDESC *
0x18000818b  lea     rcx, [rsp+480h+var_440]; this
0x180008190  call    ?Set@CDescriptor@@QEAAXPEAU_DMUS_OBJECTDESC@@PEAUIStream@@@Z; CDescriptor::Set(_DMUS_OBJECTDESC *,IStream *)
0x180008195  lea     r14, [r15+238h]
0x18000819c  mov     [rsp+480h+var_450], 0
0x1800081a5  xor     esi, esi
0x1800081a7  mov     rcx, r14; lpCriticalSection
0x1800081aa  mov     [rsp+480h+var_448], rsi
0x1800081af  call    cs:__imp_EnterCriticalSection
0x1800081b5  xor     r9d, r9d; int
0x1800081b8  lea     r8, [rsp+480h+var_450]; struct CClass **
0x1800081bd  lea     rdx, [rsp+480h+var_440]; struct CDescriptor *
0x1800081c2  mov     rcx, r15; this
0x1800081c5  call    ?GetClass@CLoader@@AEAAJPEAVCDescriptor@@PEAPEAVCClass@@H@Z; CLoader::GetClass(CDescriptor *,CClass * *,int)
0x1800081ca  mov     ebx, eax
0x1800081cc  test    eax, eax
0x1800081ce  js      short loc_1800081F3
0x1800081d0  mov     rcx, [rsp+480h+var_450]; this
0x1800081d5  lea     r8, [rsp+480h+var_448]; struct CObject **
0x1800081da  xor     r9d, r9d; struct CObject *
0x1800081dd  mov     [rsp+480h+var_460], rsi; struct IDirectMusicObject *
0x1800081e2  lea     rdx, [rsp+480h+var_440]; struct CDescriptor *
0x1800081e7  call    ?FindObject@CClass@@QEAAJPEAVCDescriptor@@PEAPEAVCObject@@PEAV3@PEAUIDirectMusicObject@@@Z; CClass::FindObject(CDescriptor *,CObject * *,CObject *,IDirectMusicObject *)
0x1800081ec  mov     rsi, [rsp+480h+var_448]
0x1800081f1  mov     ebx, eax
0x1800081f3  test    ebx, ebx
0x1800081f5  js      short loc_18000822F
0x1800081f7  mov     rcx, [rsi+0B8h]
0x1800081fe  test    rcx, rcx
0x180008201  jz      short loc_180008214
0x180008203  cmp     rcx, rdi
0x180008206  jz      short loc_180008246
0x180008208  mov     rax, [rcx]
0x18000820b  mov     rax, [rax+10h]
0x18000820f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008214  mov     [rsi+0B8h], rdi
0x18000821b  mov     rcx, rdi
0x18000821e  bts     dword ptr [rsi+10h], 9
0x180008223  mov     rax, [rdi]
0x180008226  mov     rax, [rax+8]
0x18000822a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000822f  mov     rcx, r14; lpCriticalSection
0x180008232  call    cs:__imp_LeaveCriticalSection
0x180008238  lea     rcx, [rsp+480h+var_440]; this
0x18000823d  call    ??1CDescriptor@@QEAA@XZ; CDescriptor::~CDescriptor(void)
0x180008242  mov     eax, ebx
0x180008244  jmp     short loc_180008252
0x180008246  mov     ebx, 1
0x18000824b  jmp     short loc_18000822F
0x18000824d  mov     eax, 80004003h
0x180008252  mov     rcx, [rbp+380h+var_30]
0x180008259  xor     rcx, rsp; StackCookie
0x18000825c  call    __security_check_cookie
0x180008261  mov     rbx, [rsp+480h+arg_10]
0x180008269  add     rsp, 460h
0x180008270  pop     r15
0x180008272  pop     r14
0x180008274  pop     rdi
0x180008275  pop     rsi
0x180008276  pop     rbp
0x180008277  retn
```
