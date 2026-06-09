# Recycler::Initialize(bool,JsUtil::ThreadService *)

- ea: `0x1801a9cf0`
- end: `0x1801a9da6`
- name: `?Initialize@Recycler@@QEAAX_NPEAVThreadService@JsUtil@@@Z`
- size: `182`
- prototype: `void __fastcall(Recycler *__hidden this, bool, struct JsUtil::ThreadService *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18006fa0c`

## callees

- `0x18001f668`
- `0x1801a9cf0`
- `0x1801a9dac`
- `0x1801a9e6c`
- `0x180258c4c`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1801a9d50`
- `KERNEL32!CreateEventW` at `0x1801a9d50`
- `KERNEL32!CloseHandle` at `0x1801a9d78`
- `KERNEL32!CloseHandle` at `0x1801a9d78`

## pseudocode

```c
void __fastcall Recycler::Initialize(Recycler *this, char a2, struct JsUtil::ThreadService *a3)
{
  __int64 v4; // rcx
  HANDLE *v5; // rdi

  *((_BYTE *)this + 12906) = 0;
  *((_BYTE *)this + 12902) = 1;
  *((_BYTE *)this + 12911) = a2 ^ 1;
  *((_BYTE *)this + 12912) = a2 ^ 1;
  if ( !(unsigned int)Recycler::IsConcurrentEnabled(this) )
  {
LABEL_7:
    Recycler::InitializeNonConcurrent(this);
    goto LABEL_8;
  }
  v5 = (HANDLE *)(v4 + 16144);
  if ( !JsUtil::ThreadService::HasCallback(a3) )
    *v5 = CreateEventW(0, 0, 0, 0);
  if ( !Recycler::InitializeConcurrent(this, a3) )
  {
    if ( *v5 )
    {
      CloseHandle(*v5);
      *v5 = 0;
    }
    goto LABEL_7;
  }
LABEL_8:
  *((_QWORD *)this + 68) = this;
}

```

## disassembly

```asm
0x1801a9cf0  mov     rax, rsp
0x1801a9cf3  mov     [rax+20h], rbx
0x1801a9cf7  mov     [rax+18h], r8
0x1801a9cfb  mov     [rax+10h], dl
0x1801a9cfe  mov     [rax+8], rcx
0x1801a9d02  push    rdi
0x1801a9d03  sub     rsp, 20h
0x1801a9d07  mov     al, dl
0x1801a9d09  mov     byte ptr [rcx+326Ah], 0
0x1801a9d10  xor     al, 1
0x1801a9d12  mov     byte ptr [rcx+3266h], 1
0x1801a9d19  mov     [rcx+326Fh], al
0x1801a9d1f  mov     rbx, rcx
0x1801a9d22  mov     [rcx+3270h], al
0x1801a9d28  call    ?IsConcurrentEnabled@Recycler@@AEBAHXZ; Recycler::IsConcurrentEnabled(void)
0x1801a9d2d  test    eax, eax
0x1801a9d2f  jz      short loc_1801A9D8B
0x1801a9d31  lea     rdi, [rcx+3F10h]
0x1801a9d38  mov     rcx, [rsp+28h+arg_10]; this
0x1801a9d3d  call    ?HasCallback@ThreadService@JsUtil@@QEBA_NXZ; JsUtil::ThreadService::HasCallback(void)
0x1801a9d42  test    al, al
0x1801a9d44  jnz     short loc_1801A9D5F
0x1801a9d46  xor     r9d, r9d; lpName
0x1801a9d49  xor     r8d, r8d; bInitialState
0x1801a9d4c  xor     edx, edx; bManualReset
0x1801a9d4e  xor     ecx, ecx; lpEventAttributes
0x1801a9d50  call    cs:__imp_CreateEventW
0x1801a9d57  nop     dword ptr [rax+rax+00h]
0x1801a9d5c  mov     [rdi], rax
0x1801a9d5f  mov     rdx, [rsp+28h+arg_10]; struct JsUtil::ThreadService *
0x1801a9d64  mov     rcx, rbx; this
0x1801a9d67  call    ?InitializeConcurrent@Recycler@@AEAA_NPEAVThreadService@JsUtil@@@Z; Recycler::InitializeConcurrent(JsUtil::ThreadService *)
0x1801a9d6c  test    al, al
0x1801a9d6e  jnz     short loc_1801A9D93
0x1801a9d70  mov     rcx, [rdi]; hObject
0x1801a9d73  test    rcx, rcx
0x1801a9d76  jz      short loc_1801A9D8B
0x1801a9d78  call    cs:__imp_CloseHandle
0x1801a9d7f  nop     dword ptr [rax+rax+00h]
0x1801a9d84  mov     qword ptr [rdi], 0
0x1801a9d8b  mov     rcx, rbx; this
0x1801a9d8e  call    ?InitializeNonConcurrent@Recycler@@AEAAXXZ; Recycler::InitializeNonConcurrent(void)
0x1801a9d93  mov     [rbx+220h], rbx
0x1801a9d9a  mov     rbx, [rsp+28h+arg_18]
0x1801a9d9f  add     rsp, 20h
0x1801a9da3  pop     rdi
0x1801a9da4  retn
```
