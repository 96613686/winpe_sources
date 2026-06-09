# IIS_CONFIG_RECORD::GetApplicationManager(APPLICATION_MANAGER * *)

- ea: `0x180009eb4`
- end: `0x18000a022`
- name: `?GetApplicationManager@IIS_CONFIG_RECORD@@QEAAJPEAPEAVAPPLICATION_MANAGER@@@Z`
- size: `366`
- prototype: `__int64 __fastcall(IIS_CONFIG_RECORD *__hidden this, struct APPLICATION_MANAGER **)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x180009d74`
- `0x18000e620`

## callees

- `0x180001008`
- `0x180001048`
- `0x180007090`
- `0x18000773c`
- `0x180009980`
- `0x180009eb4`

## pseudocode

```c
__int64 __fastcall IIS_CONFIG_RECORD::GetApplicationManager(IIS_CONFIG_RECORD *this, struct APPLICATION_MANAGER **a2)
{
  int v2; // esi
  APPLICATION_MANAGER *v5; // rax
  APPLICATION_MANAGER *v6; // rax
  volatile signed __int32 *v8; // rdi
  __int64 v9; // [rsp+70h] [rbp-28h]

  v2 = 0;
  *a2 = 0;
  if ( *((_QWORD *)this + 51) )
    goto LABEL_5;
  v5 = (APPLICATION_MANAGER *)operator new(0x11B0u);
  if ( !v5 )
  {
    *((_QWORD *)this + 51) = 0;
    goto LABEL_8;
  }
  v6 = APPLICATION_MANAGER::APPLICATION_MANAGER(v5);
  *((_QWORD *)this + 51) = v6;
  if ( !v6 )
  {
LABEL_8:
    v2 = -2147024882;
    goto LABEL_9;
  }
  v2 = APPLICATION_MANAGER::Create(
         (__int64)v6,
         *((const wchar_t **)this + 14),
         *((const unsigned __int16 **)this + 21),
         (IIS_CONFIG_RECORD *)((char *)this + 312),
         *((_DWORD *)this + 92) == 0,
         *((_DWORD *)this + 93),
         *((_DWORD *)this + 94),
         *((_DWORD *)this + 95),
         *((_DWORD *)this + 96),
         *((_DWORD *)this + 97),
         *((_DWORD *)this + 98),
         *((_DWORD *)this + 99),
         *((_DWORD *)this + 100),
         *((_DWORD *)this + 101),
         v9,
         *((_QWORD *)this + 35),
         *((_DWORD *)this + 76));
  if ( v2 >= 0 )
  {
LABEL_5:
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 51) + 140LL));
    *a2 = (struct APPLICATION_MANAGER *)*((_QWORD *)this + 51);
    return (unsigned int)v2;
  }
LABEL_9:
  v8 = (volatile signed __int32 *)*((_QWORD *)this + 51);
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd(v8 + 35, 0xFFFFFFFF) == 1 )
    {
      APPLICATION_MANAGER::~APPLICATION_MANAGER((APPLICATION_MANAGER *)v8);
      operator delete((void *)v8);
    }
    *((_QWORD *)this + 51) = 0;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180009eb4  mov     [rsp+arg_8], rbx
0x180009eb9  mov     [rsp+arg_10], rsi
0x180009ebe  push    rdi
0x180009ebf  sub     rsp, 90h
0x180009ec6  xor     esi, esi
0x180009ec8  mov     rdi, rdx
0x180009ecb  mov     rbx, rcx
0x180009ece  mov     [rdx], rsi
0x180009ed1  cmp     [rcx+198h], rsi
0x180009ed8  jnz     loc_180009FAE
0x180009ede  mov     ecx, 11B0h; Size
0x180009ee3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009ee8  test    rax, rax
0x180009eeb  jz      loc_180009FDD
0x180009ef1  mov     rcx, rax; this
0x180009ef4  call    ??0APPLICATION_MANAGER@@QEAA@XZ; APPLICATION_MANAGER::APPLICATION_MANAGER(void)
0x180009ef9  mov     [rbx+198h], rax
0x180009f00  mov     r10, rax
0x180009f03  test    rax, rax
0x180009f06  jz      loc_180009FE4
0x180009f0c  mov     eax, [rbx+130h]
0x180009f12  lea     r9, [rbx+138h]
0x180009f19  mov     r8, [rbx+0A8h]
0x180009f20  xor     ecx, ecx
0x180009f22  cmp     [rbx+170h], ecx
0x180009f28  mov     rdx, [rbx+70h]
0x180009f2c  mov     [rsp+98h+var_18], eax
0x180009f33  setz    cl
0x180009f36  mov     rax, [rbx+118h]
0x180009f3d  mov     [rsp+98h+var_20], rax
0x180009f42  mov     eax, [rbx+194h]
0x180009f48  mov     [rsp+98h+var_30], eax
0x180009f4c  mov     eax, [rbx+190h]
0x180009f52  mov     [rsp+98h+var_38], eax
0x180009f56  mov     eax, [rbx+18Ch]
0x180009f5c  mov     [rsp+98h+var_40], eax
0x180009f60  mov     eax, [rbx+188h]
0x180009f66  mov     [rsp+98h+var_48], eax
0x180009f6a  mov     eax, [rbx+184h]
0x180009f70  mov     [rsp+98h+var_50], eax
0x180009f74  mov     eax, [rbx+180h]
0x180009f7a  mov     [rsp+98h+var_58], eax
0x180009f7e  mov     eax, [rbx+17Ch]
0x180009f84  mov     [rsp+98h+var_60], eax
0x180009f88  mov     eax, [rbx+178h]
0x180009f8e  mov     [rsp+98h+var_68], eax
0x180009f92  mov     eax, [rbx+174h]
0x180009f98  mov     [rsp+98h+var_70], eax
0x180009f9c  mov     [rsp+98h+var_78], ecx
0x180009fa0  mov     rcx, r10
0x180009fa3  call    ?Create@APPLICATION_MANAGER@@QEAAJPEBG0PEAVMULTISZ@@HKKKKKKKHKH0W4FastCgiApplicationStdErrMode@@@Z; APPLICATION_MANAGER::Create(ushort const *,ushort const *,MULTISZ *,int,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int,ulong,int,ushort const *,FastCgiApplicationStdErrMode)
0x180009fa8  mov     esi, eax
0x180009faa  test    eax, eax
0x180009fac  js      short loc_180009FE9
0x180009fae  mov     rax, [rbx+198h]
0x180009fb5  lock inc dword ptr [rax+8Ch]
0x180009fbc  mov     rax, [rbx+198h]
0x180009fc3  mov     [rdi], rax
0x180009fc6  lea     r11, [rsp+98h+var_8]
0x180009fce  mov     eax, esi
0x180009fd0  mov     rbx, [r11+18h]
0x180009fd4  mov     rsi, [r11+20h]
0x180009fd8  mov     rsp, r11
0x180009fdb  pop     rdi
0x180009fdc  retn
0x180009fdd  mov     [rbx+198h], rsi
0x180009fe4  mov     esi, 8007000Eh
0x180009fe9  mov     rdi, [rbx+198h]
0x180009ff0  test    rdi, rdi
0x180009ff3  jz      short loc_180009FC6
0x180009ff5  or      eax, 0FFFFFFFFh
0x180009ff8  lock xadd [rdi+8Ch], eax
0x18000a000  cmp     eax, 1
0x18000a003  jnz     short loc_18000A015
0x18000a005  mov     rcx, rdi; this
0x18000a008  call    ??1APPLICATION_MANAGER@@AEAA@XZ; APPLICATION_MANAGER::~APPLICATION_MANAGER(void)
0x18000a00d  mov     rcx, rdi; Block
0x18000a010  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a015  mov     qword ptr [rbx+198h], 0
0x18000a020  jmp     short loc_180009FC6
```
