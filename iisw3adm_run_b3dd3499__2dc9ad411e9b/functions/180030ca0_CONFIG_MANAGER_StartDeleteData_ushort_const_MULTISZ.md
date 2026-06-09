# CONFIG_MANAGER::StartDeleteData(ushort const *,MULTISZ *)

- ea: `0x180030ca0`
- end: `0x180030de1`
- name: `?StartDeleteData@CONFIG_MANAGER@@QEAAXPEBGPEAVMULTISZ@@@Z`
- size: `321`
- prototype: `void __fastcall(CONFIG_MANAGER *__hidden this, const unsigned __int16 *, struct MULTISZ *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800193e4`

## callees

- `0x180001234`
- `0x180001274`
- `0x180002bbc`
- `0x1800074b0`
- `0x1800077e8`
- `0x180007b60`
- `0x180030ca0`
- `0x18006101a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d5e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180030dc0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180030dc0`
- `iisutil!PuDbgPrintError` at `0x180030dad`
- `iisutil!PuDbgPrintError` at `0x180030dad`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180030d2d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180030d2d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180030d43`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180030d43`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180030d37`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180030d37`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180030db7`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180030db7`
- `iisutil!?Copy@MULTISZ@@QEAAHAEBV1@@Z` at `0x180030d54`
- `iisutil!?Copy@MULTISZ@@QEAAHAEBV1@@Z` at `0x180030d54`

## string_xrefs

- `0x180030da2`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\changeprocessor.cxx`
- `0x180030d82`: `Couldn't queue DeleteDataThreadItemWorkItem\n`
- `0x180030d94`: `CHANGE_PROCESSOR::StartDeleteData`

## pseudocode

```c
void __fastcall CONFIG_MANAGER::StartDeleteData(CONFIG_MANAGER *this, const unsigned __int16 *a2, struct MULTISZ *a3)
{
  __int64 v3; // rbx
  WORK_QUEUE *v6; // rsi
  struct WORK_ITEM *v7; // rdi
  char *v8; // rax
  char *v9; // rbx
  int v10; // eax
  struct WORK_ITEM *v11; // [rsp+50h] [rbp+8h] BYREF

  v3 = *((_QWORD *)this + 32);
  v11 = 0;
  if ( !(unsigned int)CheckWASIsStopping() )
  {
    v6 = (WORK_QUEUE *)(v3 + 24);
    if ( (int)WORK_QUEUE::GetBlankWorkItem((WORK_QUEUE *)(v3 + 24), &v11) >= 0 )
    {
      v7 = v11;
      WORK_ITEM::SetWorkDispatchPointer(v11, (struct WORK_DISPATCH *)v3);
      *((_QWORD *)v7 + 3) = 5;
      v8 = (char *)operator new(0x70u);
      v9 = v8;
      if ( v8 )
      {
        memset_0(v8, 0, 0x70u);
        STRU::STRU((STRU *)v9);
        MULTISZ::MULTISZ((MULTISZ *)(v9 + 56));
        if ( (int)STRU::Copy((STRU *)v9, a2) >= 0 )
        {
          if ( MULTISZ::Copy((MULTISZ *)(v9 + 56), a3) )
          {
            *((_QWORD *)v7 + 11) = v9;
            v10 = WORK_QUEUE::QueueWorkItem(v6, v7);
            if ( v10 >= 0 )
              return;
            if ( (g_dwDebugFlags & 0xF) != 0 )
              PuDbgPrintError(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\changeprocessor.cxx",
                1123,
                "CHANGE_PROCESSOR::StartDeleteData",
                v10,
                "Couldn't queue DeleteDataThreadItemWorkItem\n");
          }
          else
          {
            GetLastError();
          }
        }
        MULTISZ::~MULTISZ((MULTISZ *)(v9 + 56));
        STRU::~STRU((STRU *)v9);
        operator delete(v9);
      }
    }
  }
}

```

## disassembly

```asm
0x180030ca0  mov     [rsp+arg_8], rbx
0x180030ca5  mov     [rsp+arg_10], rbp
0x180030caa  push    rsi
0x180030cab  push    rdi
0x180030cac  push    r14
0x180030cae  sub     rsp, 30h
0x180030cb2  mov     rbx, [rcx+100h]
0x180030cb9  mov     rbp, r8
0x180030cbc  mov     r14, rdx
0x180030cbf  mov     [rsp+48h+arg_0], 0
0x180030cc8  call    ?CheckWASIsStopping@@YAHXZ; CheckWASIsStopping(void)
0x180030ccd  test    eax, eax
0x180030ccf  jnz     loc_180030DCE
0x180030cd5  lea     rsi, [rbx+18h]
0x180030cd9  mov     rcx, rsi; this
0x180030cdc  lea     rdx, [rsp+48h+arg_0]; struct WORK_ITEM **
0x180030ce1  call    ?GetBlankWorkItem@WORK_QUEUE@@QEAAJPEAPEAVWORK_ITEM@@@Z; WORK_QUEUE::GetBlankWorkItem(WORK_ITEM * *)
0x180030ce6  test    eax, eax
0x180030ce8  js      loc_180030DCE
0x180030cee  mov     rdi, [rsp+48h+arg_0]
0x180030cf3  mov     rdx, rbx; struct WORK_DISPATCH *
0x180030cf6  mov     rcx, rdi; this
0x180030cf9  call    ?SetWorkDispatchPointer@WORK_ITEM@@QEAAXPEAVWORK_DISPATCH@@@Z; WORK_ITEM::SetWorkDispatchPointer(WORK_DISPATCH *)
0x180030cfe  mov     ecx, 70h ; 'p'; Size
0x180030d03  mov     qword ptr [rdi+18h], 5
0x180030d0b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030d10  mov     rbx, rax
0x180030d13  test    rax, rax
0x180030d16  jz      loc_180030DCE
0x180030d1c  xor     edx, edx; Val
0x180030d1e  mov     rcx, rax; void *
0x180030d21  lea     r8d, [rdx+70h]; Size
0x180030d25  call    memset_0
0x180030d2a  mov     rcx, rbx
0x180030d2d  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180030d33  lea     rcx, [rbx+38h]
0x180030d37  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180030d3d  mov     rdx, r14
0x180030d40  mov     rcx, rbx
0x180030d43  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180030d49  test    eax, eax
0x180030d4b  js      short loc_180030DB3
0x180030d4d  lea     rcx, [rbx+38h]
0x180030d51  mov     rdx, rbp
0x180030d54  call    cs:__imp_?Copy@MULTISZ@@QEAAHAEBV1@@Z; MULTISZ::Copy(MULTISZ const &)
0x180030d5a  test    eax, eax
0x180030d5c  jnz     short loc_180030D66
0x180030d5e  call    cs:__imp_GetLastError
0x180030d64  jmp     short loc_180030DB3
0x180030d66  mov     rdx, rdi; struct WORK_ITEM *
0x180030d69  mov     [rdi+58h], rbx
0x180030d6d  mov     rcx, rsi; this
0x180030d70  call    ?QueueWorkItem@WORK_QUEUE@@QEAAJPEAVWORK_ITEM@@@Z; WORK_QUEUE::QueueWorkItem(WORK_ITEM *)
0x180030d75  test    eax, eax
0x180030d77  jns     short loc_180030DCE
0x180030d79  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180030d80  jz      short loc_180030DB3
0x180030d82  lea     rcx, aCouldnTQueueDe; "Couldn't queue DeleteDataThreadItemWork"...
0x180030d89  mov     r8d, 463h
0x180030d8f  mov     [rsp+48h+var_20], rcx
0x180030d94  lea     r9, aChangeProcesso_2; "CHANGE_PROCESSOR::StartDeleteData"
0x180030d9b  mov     rcx, cs:g_pDebug
0x180030da2  lea     rdx, aServercommonIn_64; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180030da9  mov     [rsp+48h+var_28], eax
0x180030dad  call    cs:__imp_PuDbgPrintError
0x180030db3  lea     rcx, [rbx+38h]
0x180030db7  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180030dbd  mov     rcx, rbx
0x180030dc0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180030dc6  mov     rcx, rbx; Block
0x180030dc9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180030dce  mov     rbx, [rsp+48h+arg_8]
0x180030dd3  mov     rbp, [rsp+48h+arg_10]
0x180030dd8  add     rsp, 30h
0x180030ddc  pop     r14
0x180030dde  pop     rdi
0x180030ddf  pop     rsi
0x180030de0  retn
```
