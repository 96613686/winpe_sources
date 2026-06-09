# RawInputProvidersTracing::SpatialInputTelemetryProperties::SpatialInputTelemetryProperties(ushort const * const)

- ea: `0x1800b41f8`
- end: `0x1800b43b0`
- name: `??0SpatialInputTelemetryProperties@RawInputProvidersTracing@@QEAA@QEBG@Z`
- size: `440`
- prototype: `__int64 __fastcall(RawInputProvidersTracing::SpatialInputTelemetryProperties *__hidden this, const unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18011c440`

## callees

- `0x180068400`
- `0x180089a1c`
- `0x18008ead4`
- `0x1800b41f8`
- `0x1800b43b8`
- `0x1800f0990`
- `0x18011a808`
- `0x18011ae44`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b42e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4300`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b431f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b433e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b435e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b42e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4300`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b431f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b433e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b435e`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800b42cd`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800b42cd`

## string_xrefs

- `0x1800b428c`: `onecoreuap\internal\analog\inc\input\common\DevicePropertyHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
RawInputProvidersTracing::SpatialInputTelemetryProperties *__fastcall RawInputProvidersTracing::SpatialInputTelemetryProperties::SpatialInputTelemetryProperties(
        BYTE *this,
        const unsigned __int16 *a2)
{
  HSTRING *v3; // rdi
  HSTRING *v4; // rsi
  HSTRING *v5; // r14
  HSTRING *v6; // r15
  HSTRING *v7; // r12
  const WCHAR *v8; // rcx
  CONFIGRET Device_Interface_PropertyW; // eax
  int PropertyBufferSize; // [rsp+20h] [rbp-49h]
  ULONG v12; // [rsp+30h] [rbp-39h] BYREF
  DEVPROPTYPE PropertyType[3]; // [rsp+34h] [rbp-35h] BYREF
  RawInputProvidersTracing::SpatialInputTelemetryProperties *v14; // [rsp+40h] [rbp-29h]
  int v15; // [rsp+50h] [rbp-19h] BYREF
  LPCWSTR pszDeviceInterface[4]; // [rsp+58h] [rbp-11h] BYREF
  int v17; // [rsp+78h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v14 = (RawInputProvidersTracing::SpatialInputTelemetryProperties *)this;
  v3 = (HSTRING *)(this + 8);
  *((_QWORD *)this + 1) = 0;
  v4 = (HSTRING *)(this + 32);
  *((_QWORD *)this + 4) = 0;
  v5 = (HSTRING *)(this + 40);
  *((_QWORD *)this + 5) = 0;
  v6 = (HSTRING *)(this + 48);
  *((_QWORD *)this + 6) = 0;
  v7 = (HSTRING *)(this + 56);
  *((_QWORD *)this + 7) = 0;
  *(_QWORD *)this = a2;
  v15 = 0;
  std::wstring::wstring(pszDeviceInterface, a2);
  v17 = 0;
  if ( (int)DevicePropertyHelpers::DevicePropertyHelper::Initialize((DevicePropertyHelpers::DevicePropertyHelper *)&v15) >= 0 )
  {
    v12 = 16;
    if ( v15 )
    {
      PropertyType[0] = 0;
      v8 = (const WCHAR *)pszDeviceInterface;
      if ( pszDeviceInterface[3] > (LPCWSTR)7 )
        v8 = pszDeviceInterface[0];
      Device_Interface_PropertyW = CM_Get_Device_Interface_PropertyW(
                                     v8,
                                     &DEVPKEY_DeviceInterface_ClassGuid,
                                     PropertyType,
                                     this + 16,
                                     &v12,
                                     0);
      if ( Device_Interface_PropertyW )
        DevicePropertyHelpers::MapCrToHResult(Device_Interface_PropertyW);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5C,
        (unsigned int)"onecoreuap\\internal\\analog\\inc\\input\\common\\DevicePropertyHelpers.h",
        (const char *)0x8007139FLL,
        PropertyBufferSize);
    }
    WindowsDeleteString(*v3);
    *v3 = 0;
    DevicePropertyHelpers::DevicePropertyHelper::GetDriverProperty<HSTRING__ *>(
      (DevicePropertyHelpers::DevicePropertyHelper *)&v15,
      (struct _DEVPROPKEY *)&DEVPKEY_NAME,
      v3);
    WindowsDeleteString(*v4);
    *v4 = 0;
    DevicePropertyHelpers::DevicePropertyHelper::GetDriverProperty<HSTRING__ *>(
      (DevicePropertyHelpers::DevicePropertyHelper *)&v15,
      (struct _DEVPROPKEY *)&DEVPKEY_Device_Manufacturer,
      v4);
    WindowsDeleteString(*v5);
    *v5 = 0;
    DevicePropertyHelpers::DevicePropertyHelper::GetDriverProperty<HSTRING__ *>(
      (DevicePropertyHelpers::DevicePropertyHelper *)&v15,
      (struct _DEVPROPKEY *)&DEVPKEY_Device_Model,
      v5);
    WindowsDeleteString(*v6);
    *v6 = 0;
    DevicePropertyHelpers::DevicePropertyHelper::GetDriverProperty<HSTRING__ *>(
      (DevicePropertyHelpers::DevicePropertyHelper *)&v15,
      (struct _DEVPROPKEY *)&DEVPKEY_Device_FirmwareVersion,
      v6);
    WindowsDeleteString(*v7);
    *v7 = 0;
    DevicePropertyHelpers::DevicePropertyHelper::GetDriverProperty<HSTRING__ *>(
      (DevicePropertyHelpers::DevicePropertyHelper *)&v15,
      (struct _DEVPROPKEY *)&DEVPKEY_Device_DriverVersion,
      v7);
  }
  std::wstring::_Tidy_deallocate(pszDeviceInterface);
  return (RawInputProvidersTracing::SpatialInputTelemetryProperties *)this;
}

```

## disassembly

```asm
0x1800b41f8  mov     [rsp-8+arg_10], rbx
0x1800b41fd  push    rbp
0x1800b41fe  push    rsi
0x1800b41ff  push    rdi
0x1800b4200  push    r12
0x1800b4202  push    r13
0x1800b4204  push    r14
0x1800b4206  push    r15
0x1800b4208  lea     rbp, [rsp-27h]
0x1800b420d  sub     rsp, 90h
0x1800b4214  mov     rax, cs:__security_cookie
0x1800b421b  xor     rax, rsp
0x1800b421e  mov     [rbp+57h+var_40], rax
0x1800b4222  mov     rbx, rcx
0x1800b4225  mov     [rbp+57h+var_80], rcx
0x1800b4229  lea     rdi, [rcx+8]
0x1800b422d  xor     r13d, r13d
0x1800b4230  mov     [rdi], r13
0x1800b4233  lea     rsi, [rcx+20h]
0x1800b4237  mov     [rsi], r13
0x1800b423a  lea     r14, [rcx+28h]
0x1800b423e  mov     [r14], r13
0x1800b4241  lea     r15, [rcx+30h]
0x1800b4245  mov     [r15], r13
0x1800b4248  lea     r12, [rcx+38h]
0x1800b424c  mov     [r12], r13
0x1800b4250  mov     [rcx], rdx
0x1800b4253  mov     [rbp+57h+var_70], r13d
0x1800b4257  lea     rcx, [rbp+57h+pszDeviceInterface]
0x1800b425b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b4260  mov     [rbp+57h+var_48], r13d
0x1800b4264  lea     rcx, [rbp+57h+var_70]; this
0x1800b4268  call    ?Initialize@DevicePropertyHelper@DevicePropertyHelpers@@QEAAJXZ; DevicePropertyHelpers::DevicePropertyHelper::Initialize(void)
0x1800b426d  test    eax, eax
0x1800b426f  js      loc_1800B437C
0x1800b4275  mov     [rbp+57h+var_90], 10h
0x1800b427c  cmp     [rbp+57h+var_70], r13d
0x1800b4280  jnz     short loc_1800B429E
0x1800b4282  mov     rcx, [rbp+5Fh]; this
0x1800b4286  mov     r9d, 8007139Fh; char *
0x1800b428c  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\analog\\inc\\inpu"...
0x1800b4293  lea     edx, [r13+5Ch]; void *
0x1800b4297  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b429c  jmp     short loc_1800B42DE
0x1800b429e  mov     [rbp+57h+PropertyType], r13d
0x1800b42a2  lea     rcx, [rbp+57h+pszDeviceInterface]
0x1800b42a6  cmp     [rbp+57h+var_50], 7
0x1800b42ab  cmova   rcx, [rbp+57h+pszDeviceInterface]; pszDeviceInterface
0x1800b42b0  lea     r9, [rbx+10h]; PropertyBuffer
0x1800b42b4  mov     [rsp+0C0h+ulFlags], r13d; ulFlags
0x1800b42b9  lea     rax, [rbp+57h+var_90]
0x1800b42bd  mov     [rsp+0C0h+PropertyBufferSize], rax; PropertyBufferSize
0x1800b42c2  lea     r8, [rbp+57h+PropertyType]; PropertyType
0x1800b42c6  lea     rdx, DEVPKEY_DeviceInterface_ClassGuid; PropertyKey
0x1800b42cd  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x1800b42d3  test    eax, eax
0x1800b42d5  jz      short loc_1800B42DE
0x1800b42d7  mov     ecx, eax
0x1800b42d9  call    DevicePropertyHelpers__MapCrToHResult
0x1800b42de  mov     rcx, [rdi]; string
0x1800b42e1  call    cs:__imp_WindowsDeleteString
0x1800b42e7  mov     [rdi], r13
0x1800b42ea  mov     r8, rdi
0x1800b42ed  lea     rdx, DEVPKEY_NAME
0x1800b42f4  lea     rcx, [rbp+57h+var_70]
0x1800b42f8  call    ??$GetDriverProperty@PEAUHSTRING__@@@DevicePropertyHelper@DevicePropertyHelpers@@QEBAJAEBU_DEVPROPKEY@@PEAPEAUHSTRING__@@@Z; DevicePropertyHelpers::DevicePropertyHelper::GetDriverProperty<HSTRING__ *>(_DEVPROPKEY const &,HSTRING__ * *)
0x1800b42fd  mov     rcx, [rsi]; string
0x1800b4300  call    cs:__imp_WindowsDeleteString
0x1800b4306  mov     [rsi], r13
0x1800b4309  mov     r8, rsi
0x1800b430c  lea     rdx, DEVPKEY_Device_Manufacturer
0x1800b4313  lea     rcx, [rbp+57h+var_70]
0x1800b4317  call    ??$GetDriverProperty@PEAUHSTRING__@@@DevicePropertyHelper@DevicePropertyHelpers@@QEBAJAEBU_DEVPROPKEY@@PEAPEAUHSTRING__@@@Z; DevicePropertyHelpers::DevicePropertyHelper::GetDriverProperty<HSTRING__ *>(_DEVPROPKEY const &,HSTRING__ * *)
0x1800b431c  mov     rcx, [r14]; string
0x1800b431f  call    cs:__imp_WindowsDeleteString
0x1800b4325  mov     [r14], r13
0x1800b4328  mov     r8, r14
0x1800b432b  lea     rdx, DEVPKEY_Device_Model
0x1800b4332  lea     rcx, [rbp+57h+var_70]
0x1800b4336  call    ??$GetDriverProperty@PEAUHSTRING__@@@DevicePropertyHelper@DevicePropertyHelpers@@QEBAJAEBU_DEVPROPKEY@@PEAPEAUHSTRING__@@@Z; DevicePropertyHelpers::DevicePropertyHelper::GetDriverProperty<HSTRING__ *>(_DEVPROPKEY const &,HSTRING__ * *)
0x1800b433b  mov     rcx, [r15]; string
0x1800b433e  call    cs:__imp_WindowsDeleteString
0x1800b4344  mov     [r15], r13
0x1800b4347  mov     r8, r15
0x1800b434a  lea     rdx, DEVPKEY_Device_FirmwareVersion
0x1800b4351  lea     rcx, [rbp+57h+var_70]
0x1800b4355  call    ??$GetDriverProperty@PEAUHSTRING__@@@DevicePropertyHelper@DevicePropertyHelpers@@QEBAJAEBU_DEVPROPKEY@@PEAPEAUHSTRING__@@@Z; DevicePropertyHelpers::DevicePropertyHelper::GetDriverProperty<HSTRING__ *>(_DEVPROPKEY const &,HSTRING__ * *)
0x1800b435a  mov     rcx, [r12]; string
0x1800b435e  call    cs:__imp_WindowsDeleteString
0x1800b4364  mov     [r12], r13
0x1800b4368  mov     r8, r12
0x1800b436b  lea     rdx, DEVPKEY_Device_DriverVersion
0x1800b4372  lea     rcx, [rbp+57h+var_70]
0x1800b4376  call    ??$GetDriverProperty@PEAUHSTRING__@@@DevicePropertyHelper@DevicePropertyHelpers@@QEBAJAEBU_DEVPROPKEY@@PEAPEAUHSTRING__@@@Z; DevicePropertyHelpers::DevicePropertyHelper::GetDriverProperty<HSTRING__ *>(_DEVPROPKEY const &,HSTRING__ * *)
0x1800b437b  nop
0x1800b437c  lea     rcx, [rbp+57h+pszDeviceInterface]
0x1800b4380  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b4385  nop
0x1800b4386  mov     rax, rbx
0x1800b4389  mov     rcx, [rbp+57h+var_40]
0x1800b438d  xor     rcx, rsp; StackCookie
0x1800b4390  call    __security_check_cookie
0x1800b4395  mov     rbx, [rsp+0C0h+arg_10]
0x1800b439d  add     rsp, 90h
0x1800b43a4  pop     r15
0x1800b43a6  pop     r14
0x1800b43a8  pop     r13
0x1800b43aa  pop     r12
0x1800b43ac  pop     rdi
0x1800b43ad  pop     rsi
0x1800b43ae  pop     rbp
0x1800b43af  retn
```
