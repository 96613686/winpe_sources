# CIncomingConnectionsTask::CanRunTask(HWND__ * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x18001fa60`
- end: `0x18001fb55`
- name: `?CanRunTask@CIncomingConnectionsTask@@UEAAJQEAUHWND__@@QEAU_GUID@@W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `245`
- prototype: `__int64 __fastcall(CIncomingConnectionsTask *, __int64, __int64, char, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800114d8`
- `0x18001f8ec`
- `0x18001fa60`
- `0x18002f382`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18001fb3d`
- `rtutils!TracePrintfExA` at `0x18001fb3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001fac6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001fac6`

## string_xrefs

- `0x18001fb31`: `CIncomingConnectionsTask::CanRunTask: returns hr = %#x`

## pseudocode

```c
__int64 __fastcall CIncomingConnectionsTask::CanRunTask(
        CIncomingConnectionsTask *a1,
        __int64 a2,
        __int64 a3,
        char a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9)
{
  int v11; // ebx
  char *v12; // rax
  char *v13; // rbx

  *a9 = 0;
  if ( (a4 & 0x22) != 0 )
  {
    if ( (unsigned int)CIncomingConnectionsTask::CanAllowICC(a1) )
    {
      *((_QWORD *)a1 + 8) = a8;
      v11 = HrEnsureTearOffInterfaceLoaded(a8, &IID_IXWizardPropertyBag, (char *)a1 + 72);
      if ( v11 >= 0 )
      {
        v12 = (char *)CoTaskMemAlloc(0x60u);
        v13 = v12;
        if ( v12 )
        {
          memset_0(v12 + 8, 0, 0x58u);
          *(_DWORD *)v13 = 96;
          *((_DWORD *)v13 + 1) = 524292;
          *((_QWORD *)v13 + 2) = hInst;
          *((_QWORD *)v13 + 1) = a2;
          *((_QWORD *)v13 + 4) = 3040;
          *((_QWORD *)v13 + 3) = 10011;
          *((_QWORD *)v13 + 11) = 0;
          *a9 = v13;
          v11 = 0;
        }
        else
        {
          v11 = -2147024882;
        }
      }
    }
    else
    {
      v11 = 1;
    }
  }
  else
  {
    v11 = -2147418113;
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "CIncomingConnectionsTask::CanRunTask: returns hr = %#x", v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001fa60  mov     [rsp+arg_0], rbx
0x18001fa65  mov     [rsp+arg_8], rsi
0x18001fa6a  push    rdi
0x18001fa6b  sub     rsp, 20h
0x18001fa6f  mov     rdi, [rsp+28h+arg_40]
0x18001fa74  mov     rsi, rdx
0x18001fa77  mov     rbx, rcx
0x18001fa7a  mov     qword ptr [rdi], 0
0x18001fa81  test    r9b, 22h
0x18001fa85  jnz     short loc_18001FA91
0x18001fa87  mov     ebx, 8000FFFFh
0x18001fa8c  jmp     loc_18001FB23
0x18001fa91  call    ?CanAllowICC@CIncomingConnectionsTask@@IEAAHXZ; CIncomingConnectionsTask::CanAllowICC(void)
0x18001fa96  test    eax, eax
0x18001fa98  jnz     short loc_18001FAA2
0x18001fa9a  lea     ebx, [rax+1]
0x18001fa9d  jmp     loc_18001FB23
0x18001faa2  mov     rcx, [rsp+28h+arg_38]
0x18001faa7  lea     r8, [rbx+48h]
0x18001faab  lea     rdx, IID_IXWizardPropertyBag
0x18001fab2  mov     [rbx+40h], rcx
0x18001fab6  call    HrEnsureTearOffInterfaceLoaded
0x18001fabb  mov     ebx, eax
0x18001fabd  test    eax, eax
0x18001fabf  js      short loc_18001FB23
0x18001fac1  mov     ecx, 60h ; '`'; cb
0x18001fac6  call    cs:__imp_CoTaskMemAlloc
0x18001facc  mov     rbx, rax
0x18001facf  test    rax, rax
0x18001fad2  jz      short loc_18001FB1E
0x18001fad4  xor     edx, edx; Val
0x18001fad6  lea     rcx, [rax+8]; void *
0x18001fada  lea     r8d, [rdx+58h]; Size
0x18001fade  call    memset_0
0x18001fae3  mov     dword ptr [rbx], 60h ; '`'
0x18001fae9  mov     dword ptr [rbx+4], 80004h
0x18001faf0  mov     rcx, cs:hInst
0x18001faf7  mov     [rbx+10h], rcx
0x18001fafb  mov     [rbx+8], rsi
0x18001faff  mov     qword ptr [rbx+20h], 0BE0h
0x18001fb07  mov     qword ptr [rbx+18h], 271Bh
0x18001fb0f  mov     qword ptr [rbx+58h], 0
0x18001fb17  mov     [rdi], rbx
0x18001fb1a  xor     ebx, ebx
0x18001fb1c  jmp     short loc_18001FB23
0x18001fb1e  mov     ebx, 8007000Eh
0x18001fb23  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001fb29  cmp     ecx, 0FFFFFFFFh
0x18001fb2c  jz      short loc_18001FB43
0x18001fb2e  mov     r9d, ebx
0x18001fb31  lea     r8, aCincomingconne_3; "CIncomingConnectionsTask::CanRunTask: r"...
0x18001fb38  mov     edx, 0Ch; dwFlags
0x18001fb3d  call    cs:__imp_TracePrintfExA
0x18001fb43  mov     rsi, [rsp+28h+arg_8]
0x18001fb48  mov     eax, ebx
0x18001fb4a  mov     rbx, [rsp+28h+arg_0]
0x18001fb4f  add     rsp, 20h
0x18001fb53  pop     rdi
0x18001fb54  retn
```
